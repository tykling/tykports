# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	certgrinder
PORTVERSION=	0.17.2
PORTREVISION=	5
CATEGORIES=	sysutils python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	Client for getting LetsEncrypt certificates from a Certgrinderd server

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}cryptography>=3.3.2:security/py-cryptography@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}dnspython>=1.16.0:dns/py-dnspython@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pid>=3.0.4:devel/py-pid@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}yaml>=5.4.1:devel/py-yaml@${PY_FLAVOR}

# 3.7, 3.8, 3.9, 3.10
USES=		python:3.7+
USE_PYTHON=	autoplist distutils concurrent

USERS=		certgrinder
GROUPS=		certgrinder

PLIST_FILES=	"@sample ${ETCDIR}/certgrinder.conf.sample" \
		"@dir ${ETCDIR}" \
		"@dir ${ETCDIR}/hooks.d" \
		"@dir ${ETCDIR}/certificates"

OPTIONS_DEFINE=		MANPAGES
OPTIONS_DEFAULT=	MANPAGES
MANPAGES_PLIST_FILES=	share/man/man8/certgrinder.8.gz

do-install:
	${INSTALL} -d -o certgrinder -g certgrinder ${STAGEDIR}${ETCDIR}
	${INSTALL} -d -o certgrinder -g certgrinder ${STAGEDIR}${ETCDIR}/hooks.d
	${INSTALL} -d -o certgrinder -g certgrinder -m 0750 ${STAGEDIR}${ETCDIR}/certificates

post-install:
	${INSTALL_DATA} ${WRKSRC}/certgrinder/certgrinder.conf.dist ${STAGEDIR}${ETCDIR}/certgrinder.conf.sample

post-install-MANPAGES-on:
	${INSTALL_MAN} ${WRKSRC}/man/certgrinder.8 ${STAGEDIR}${PREFIX}/share/man/man8

.include <bsd.port.mk>
