# $NetBSD: Makefile,v 1.142 2018/01/02 05:37:23 maya Exp $

DISTNAME=	gnupg-1.4.22
PKGREVISION=	2
CATEGORIES=	security
MASTER_SITES=	ftp://ftp.gnupg.org/gcrypt/gnupg/
MASTER_SITES+=	http://gd.tuwien.ac.at/privacy/gnupg/gnupg/
MASTER_SITES+=	ftp://ftp.ring.gr.jp/pub/net/gnupg/gnupg/
EXTRACT_SUFX=	.tar.bz2

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://www.gnupg.org/
COMMENT=	GNU Privacy Guard, public-Key encryption and digital signatures
LICENSE=	gnu-gpl-v3

GNU_CONFIGURE=		yes
USE_PKGLOCALEDIR=	yes
USE_TOOLS+=		gmake msgfmt
CONFIGURE_ARGS+=	--with-mailprog=/usr/sbin/sendmail
TEST_TARGET=		check
INFO_FILES=		yes

EXTRACT_ONLY=	${DISTNAME}${EXTRACT_SUFX}

.include "options.mk"

.if ${OPSYS} == "SunOS" || (${OPSYS} == "NetBSD" && !empty(OS_VERSION:M1.[0-6]*))
CONFIGURE_ARGS+=	--disable-gnupg-iconv
.endif

.if (${OPSYS} == "AIX" || ${OPSYS} == "Darwin" || ${OPSYS} == "SunOS") \
    && defined(ABI) && ${ABI} == 64
CONFIGURE_ARGS+=	--disable-asm
.endif

.if !empty(USE_CROSS_COMPILE:M[yY][eE][sS])
CONFIGURE_ENV+=		CC_FOR_BUILD=${NATIVE_CC:Q}
.endif

post-install:
	${INSTALL_DATA} ${WRKSRC}/doc/DETAILS \
	    ${DESTDIR}${PREFIX}/share/gnupg

.include "../../devel/readline/buildlink3.mk"
.include "../../converters/libiconv/buildlink3.mk"
.include "../../devel/gettext-lib/buildlink3.mk"
.include "../../devel/zlib/buildlink3.mk"
.include "../../archivers/bzip2/buildlink3.mk"

.include "../../mk/bsd.pkg.mk"
