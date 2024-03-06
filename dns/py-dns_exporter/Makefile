# Created by: Thomas Steen Rasmussen <thomas@gibfest.dk>
# $FreeBSD$

PORTNAME=	dns_exporter
DISTVERSION=	1.0.0rc2
CATEGORIES=	dns python
MASTER_SITES=	PYPI
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	thomas@gibfest.dk
COMMENT=	A multi-target Prometheus exporter with an exclusive focus on DNS monitoring.
WWW=	https://github.com/tykling/dns_exporter

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}setuptools>0:devel/py-setuptools@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>0:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}setuptools-scm>0:devel/py-setuptools-scm@${PY_FLAVOR}

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}prometheus-client>=0.17.1:net-mgmt/py-prometheus-client@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}dnspython>=2.5.0:dns/py-dnspython@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}yaml>=6.0:devel/py-yaml@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pysocks>=1.7.1:net/py-pysocks@${PY_FLAVOR}

USES=		python:3.9+
USE_PYTHON=	autoplist pep517

ETCDIR="${PREFIX}/etc"

PLIST_FILES=	"@sample ${ETCDIR}/dns_exporter.yml.sample"

SUB_FILES=      pkg-message
SUB_LIST=       ETCDIR=${ETCDIR} PORTVERSION=${PORTVERSION}

post-install:
	${INSTALL_DATA} ${WRKSRC}/src/dns_exporter/dns_exporter_example.yml ${STAGEDIR}${ETCDIR}/dns_exporter.yml.sample


.include <bsd.port.mk>
