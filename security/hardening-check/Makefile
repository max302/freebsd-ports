# Created by: Jov <amutu@amutu.com>
# $FreeBSD$

PORTNAME=	hardening-check
PORTVERSION=	2.6
CATEGORIES=	security
MASTER_SITES=	http://http.debian.net/debian/pool/main/h/hardening-wrapper/
DISTNAME=	hardening-wrapper_${PORTVERSION}

MAINTAINER=	amutu@amutu.com
COMMENT=	Check binaries for security hardening features

LICENSE=	GPLv2+

USES=		tar:xz shebangfix perl5

SHEBANG_LANG=	perl
SHEBANG_FILES=	${PORTNAME}

NO_BUILD=	yes
PLIST_FILES=	bin/${PORTNAME}

WRKSRC=		${WRKDIR}/hardening-wrapper

post-patch:
	${REINPLACE_CMD} -e 's/die "List of libc functions not defined/#&/' \
		-e 's/^libc./& Not supported on FreeBSD now./' \
		-e 's/against glibc)./& This function is currently Not supported on FreeBSD./' \
		${WRKSRC}/${PORTNAME}

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
