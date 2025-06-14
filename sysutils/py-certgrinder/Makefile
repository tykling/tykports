# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	certgrinder
PORTVERSION=	0.21.0
CATEGORIES=	sysutils python
MASTER_SITES=	PYPI
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	Client for getting LetsEncrypt certificates from a Certgrinderd server

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}setuptools>0:devel/py-setuptools@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>0:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}setuptools-scm>0:devel/py-setuptools-scm@${PY_FLAVOR}

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}dnspython>=2.6.1:dns/py-dnspython@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pid>=3.0.4:devel/py-pid@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pyyaml>=6.0:devel/py-pyyaml@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pydantic-settings>=2.6:devel/py-pydantic-settings@${PY_FLAVOR}

USES=		python:3.10+
USE_PYTHON=	autoplist pep517 cryptography

USERS=		certgrinder
GROUPS=		certgrinder

PLIST_FILES=	"${ETCDIR}/certgrinder.conf.sample" \
		"@dir(certgrinder,certgrinder,755) ${ETCDIR}" \
		"@dir(certgrinder,certgrinder,755) ${ETCDIR}/hooks.d" \
		"@dir(certgrinder,certgrinder,750) ${ETCDIR}/certificates" \
		"@dir(certgrinder,certgrinder,700) ${ETCDIR}/.ssh"

OPTIONS_DEFINE=		MANPAGES
OPTIONS_DEFAULT=	MANPAGES
MANPAGES_PLIST_FILES=	share/man/man8/certgrinder.8.gz

SUB_FILES=      pkg-message
SUB_LIST=       ETCDIR=${ETCDIR} PORTVERSION=${PORTVERSION}

post-install:
	${MKDIR} ${STAGEDIR}${ETCDIR}
	${MKDIR} ${STAGEDIR}${ETCDIR}/hooks.d
	${MKDIR} ${STAGEDIR}${ETCDIR}/certificates
	${MKDIR} ${STAGEDIR}${ETCDIR}/.ssh
	${INSTALL_DATA} ${WRKSRC}/certgrinder/certgrinder.conf.dist ${STAGEDIR}${ETCDIR}/certgrinder.conf.sample

post-install-MANPAGES-on:
	${INSTALL_MAN} ${WRKSRC}/man/certgrinder.8 ${STAGEDIR}${PREFIX}/share/man/man8

.include <bsd.port.mk>
