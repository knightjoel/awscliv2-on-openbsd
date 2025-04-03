COMMENT =		Python bindings for the AWS Common Runtime

MODPY_EGG_VERSION =	0.25.4
DISTNAME =		awscrt-${MODPY_EGG_VERSION}
PKGNAME =		py-awscrt-${MODPY_EGG_VERSION}

CATEGORIES =		devel

HOMEPAGE =		https://github.com/awslabs/aws-crt-python
MAINTAINER =		Joel Knight <knight.joel@gmail.com>

# Apache 2.0
PERMIT_PACKAGE =	Yes

WANTLIB +=		pthread

MODULES =		lang/python \
			devel/cmake

MODPY_PI =		Yes
MODPY_PYBUILD =		setuptools

FLAVORS =		python3
FLAVOR =		python3

BUILD_DEPENDS +=	devel/cmake

# aws-lc <https://github.com/aws/aws-lc>, which is vendored into the
# Python CRT bindings, isn't compatible with exec-only.
USE_NOEXECONLY =	Yes

NO_TEST =		Yes

# pass in CONFIGURE_ARGS defined by the cmake module
MAKE_ENV +=		CMAKE_ARGS="${CONFIGURE_ARGS}"

do-configure:
	# empty to avoid running cmake.port.mk do-configure

do-build:
	@${MODPY_BUILD_TARGET}

do-install:
	@${MODPY_INSTALL_TARGET}

.include <bsd.port.mk>
