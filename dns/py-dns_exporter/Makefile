# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	dns_exporter
DISTVERSION=	1.1.0
CATEGORIES=	dns python
MASTER_SITES=	PYPI
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	Multi-target Prometheus exporter focused on DNS monitoring

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}setuptools>0:devel/py-setuptools@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>0:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}setuptools-scm>0:devel/py-setuptools-scm@${PY_FLAVOR}

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}prometheus-client>=0.17.1:net-mgmt/py-prometheus-client@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}dnspython>=2.7.0:dns/py-dnspython@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pyyaml>=6.0:devel/py-pyyaml@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pysocks>=1.7.1:net/py-pysocks@${PY_FLAVOR}

USES=		python:3.9+
USE_PYTHON=	autoplist pep517
USE_RC_SUBR=	dns_exporter

ETCDIR="${PREFIX}/etc"

PLIST_FILES=	"@sample ${ETCDIR}/dns_exporter.yml.sample"

SUB_FILES=      pkg-message
SUB_LIST=       ETCDIR=${ETCDIR} PORTVERSION=${PORTVERSION} PYTHON_CMD=${PYTHON_CMD}

post-install:
	${INSTALL_DATA} ${WRKSRC}/src/dns_exporter/dns_exporter_example.yml ${STAGEDIR}${ETCDIR}/dns_exporter.yml.sample

.include <bsd.port.mk>
