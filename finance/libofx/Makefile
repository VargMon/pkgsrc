# $NetBSD: Makefile,v 1.25 2018/01/07 20:59:40 joerg Exp $

DISTNAME=	libofx-0.9.10
PKGREVISION=	7
CATEGORIES=	finance devel
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=libofx/}

MAINTAINER=	gary@duzan.org
HOMEPAGE=	http://libofx.sourceforge.net/
COMMENT=	OFX (Open Financial eXchange) Library
LICENSE=	gnu-gpl-v2

GNU_CONFIGURE=		yes
CONFIGURE_ARGS+=	--with-opensp-includes=${BUILDLINK_PREFIX.opensp}/include/OpenSP \
			--with-opensp-libs=${BUILDLINK_PREFIX.opensp}/libs
USE_LANGUAGES=		c c++
USE_TOOLS+=		pkg-config
USE_LIBTOOL=		yes

post-extract:
	${CHMOD} -R go-w ${WRKSRC}

.include "../../textproc/libxml++1/buildlink3.mk"
.include "../../textproc/opensp/buildlink3.mk"
.include "../../www/curl/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
