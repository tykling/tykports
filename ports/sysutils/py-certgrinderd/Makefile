# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	certgrinderd
PORTVERSION=	0.13.2
CATEGORIES=	sysutils
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	Certgrinderd server for use with py-certgrinder client

LICENSE=	BSD3CLAUSE

USERS=	certgrinderd
GROUPS=	certgrinderd

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}certbot>=${ACME_VERSION},1:security/py-certbot@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}yaml>=5.1.2:devel/py-yaml@${PY_FLAVOR}

# 3.7, 3.8
USES=		python:3.7+
USE_PYTHON=	autoplist distutils

post-install:
	${INSTALL_MAN} ${WRKSRC}/man/certgrinderd.8 ${STAGEDIR}${MAN8PREFIX}/man/man8
	${CAT} ${WRKSRC}/certgrinderd/certgrinderd.conf.dist >> ${STAGEDIR}etc/certgrinderd.conf.sample

.include <bsd.port.mk>
