# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	certgrinderd
PORTVERSION=	0.13.1
CATEGORIES=	sysutils
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	Certgrinderd server for use with py-certgrinder client

LICENSE=	BSD3CLAUSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}certbot>=${ACME_VERSION},1:security/py-certbot@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}yaml>=5.1.2:devel/py-yaml@${PY_FLAVOR}

# 3.7, 3.8
USES=		python:3.7+
USE_PYTHON=	autoplist distutils

.include <bsd.port.mk>
