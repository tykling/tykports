# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	pfctl_exporter
PORTVERSION=	0.5.1
PORTREVISION=	2
CATEGORIES=	sysutils python
MASTER_SITES=	PYPI
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	Prometheus exporter for the pf firewall using pfctl(8) data

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}setuptools>0:devel/py-setuptools@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>0:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}setuptools-scm>0:devel/py-setuptools-scm@${PY_FLAVOR}

RUN_DEPENDS=   ${PYTHON_PKGNAMEPREFIX}prometheus-client>=0.17.1:net-mgmt/py-prometheus-client@${PY_FLAVOR}

SUB_LIST=	PYTHON_CMD=${PYTHON_CMD}
USES=		python:3.9+
USE_PYTHON=	autoplist pep517
USE_RC_SUBR=	pfctl_exporter

.include <bsd.port.mk>
