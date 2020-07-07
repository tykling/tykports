# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	certgrinder
PORTVERSION=	0.13.1
CATEGORIES=	sysutils
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	The client part of the certgrinder project. use with 'certgrinderd' package on the serverside

LICENSE=	BSD3CLAUSE

USES=		python:3.7+ # 3.7, 3.8
USE_PYTHON=	autoplist distutils

RUN_DEPENDS=${PYTHON_PKGNAMEPREFIX}cryptography>=2.6.1:security/py-cryptography@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}dnspython>=1.16.0:dns/py-dnspython@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}pid>=2.2.3:devel/py-pid@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}yaml>=5.1.2:devel/py-yaml@${PY_FLAVOR}

.include <bsd.port.mk>
