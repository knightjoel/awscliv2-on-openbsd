COMMENT =		universal command line environment v2 for AWS

MODPY_DISTV =		2.27.42
PKGNAME =		awscli-${MODPY_DISTV}

GH_ACCOUNT =		aws
GH_PROJECT =		aws-cli
GH_TAGNAME =		${MODPY_DISTV}

CATEGORIES =		sysutils

HOMEPAGE =		https://aws.amazon.com/cli/
MAINTAINER =		Joel Knight <knight.joel@gmail.com>

# Apache 2.0
PERMIT_PACKAGE =	Yes

MODULES =		lang/python

MODPY_PYBUILD =		flit_core

RUN_DEPENDS +=		devel/py-awscrt=0.26.1
RUN_DEPENDS +=		devel/py-colorama${MODPY_FLAVOR}
RUN_DEPENDS +=		textproc/py-docutils${MODPY_FLAVOR}
RUN_DEPENDS +=		security/py-cryptography${MODPY_FLAVOR}
RUN_DEPENDS +=		textproc/py-ruamel.yaml${MODPY_FLAVOR}
RUN_DEPENDS +=		textproc/py-ruamel.yaml.clib${MODPY_FLAVOR}
RUN_DEPENDS +=		devel/py-prompt_toolkit${MODPY_FLAVOR}
RUN_DEPENDS +=		sysutils/py-distro${MODPY_FLAVOR}
RUN_DEPENDS +=		devel/py-dateutil${MODPY_FLAVOR}
RUN_DEPENDS +=		devel/py-jmespath${MODPY_FLAVOR}
RUN_DEPENDS +=		www/py-urllib3${MODPY_FLAVOR}
RUN_DEPENDS +=		devel/py-zipp${MODPY_FLAVOR}
BUILD_DEPENDS += 	${RUN_DEPENDS}

NO_TEST =		Yes

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/bash-completion/completions
	mv ${PREFIX}/bin/aws_bash_completer \
		${PREFIX}/share/bash-completion/completions/awscli
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/awscli
	mv ${PREFIX}/bin/aws_zsh_completer.sh \
		${PREFIX}/share/examples/awscli
	rm ${PREFIX}/bin/aws.cmd

.include <bsd.port.mk>
