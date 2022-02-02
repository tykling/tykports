# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	certgrinderd
PORTVERSION=	0.17.2
PORTREVISION=	2
CATEGORIES=	sysutils python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	Server for getting LetsEncrypt certificates for Certgrinder clients

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}certbot>=${ACME_VERSION},1:security/py-certbot@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}yaml>=5.4.1:devel/py-yaml@${PY_FLAVOR}

# 3.7, 3.8, 3.9, 3.10
USES=		python:3.7+
USE_PYTHON=	autoplist distutils

USERS=		certgrinderd
GROUPS=		certgrinderd

PLIST_FILES=	"${ETCDIR}/certgrinderd.conf.sample" \
		"@dir(certgrinderd,certgrinderd,755) ${ETCDIR}" \
		"@dir(certgrinderd,certgrinderd,700) ${ETCDIR}/.ssh"

OPTIONS_DEFINE=		MANPAGES
OPTIONS_DEFAULT=	MANPAGES
MANPAGES_PLIST_FILES=	share/man/man8/certgrinderd.8.gz

SUB_FILES=      pkg-message
SUB_LIST=       ETCDIR=${ETCDIR} PORTVERSION=${PORTVERSION}

post-install:
	${MKDIR} ${STAGEDIR}${ETCDIR}
	${MKDIR} ${STAGEDIR}${ETCDIR}/.ssh
	${INSTALL_DATA} ${WRKSRC}/certgrinderd/certgrinderd.conf.dist ${STAGEDIR}${ETCDIR}/certgrinderd.conf.sample

post-install-MANPAGES-on:
	${INSTALL_MAN} ${WRKSRC}/man/certgrinderd.8 ${STAGEDIR}${PREFIX}/share/man/man8

.include <bsd.port.mk>
