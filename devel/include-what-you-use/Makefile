# Created by: Kubilay Kocak <koobs@FreeBSD.org>
# $FreeBSD$

PORTNAME=	include-what-you-use
PORTVERSION=	0.7
PORTREVISION=	1
CATEGORIES=	devel

MAINTAINER=	koobs@FreeBSD.org
COMMENT=	Tool for use with clang to analyze #includes in C and C++ source files

LICENSE=	NCSA
LICENSE_FILE=	${WRKSRC}/LICENSE.TXT

BUILD_DEPENDS=	clang39:devel/llvm39
RUN_DEPENDS=	clang39:devel/llvm39

BROKEN_powerpc64=	fails to compile: cc1plus: unrecognized command line option "-std=c++11"

USES=		cmake:outsource ncurses python:run shebangfix
USE_GITHUB=	yes

SHEBANG_FILES=	fix_includes.py \
		iwyu_tool.py

GH_TAGNAME=	clang_3.9

CMAKE_ARGS+=	-DIWYU_LLVM_INCLUDE_PATH=${LOCALBASE}/llvm39/include \
		-DIWYU_LLVM_LIB_PATH=${LOCALBASE}/llvm39/lib

.include <bsd.port.mk>
