# $NetBSD: Makefile,v 1.5 2011/01/19 11:55:50 plunky Exp $

PROG=		lua
SRCS=		lua.c
BINDIR=		/usr/bin

.if defined(__MINIX)
# BJG - lua has to be dynamic to allow loading modules
# Diagnosed by Marc Balmer
LDSTATIC=-dynamic
.endif # defined(__MINIX)

CPPFLAGS+=	-DLUA_USE_READLINE

LDADD+=		-llua -lm -ledit -lterminfo
DPADD+=		${LIBLUA} ${LIBM} ${LIBEDIT} ${LIBTERMINFO}

.include <bsd.own.mk>

.PATH:		${NETBSDSRCDIR}/external/mit/lua/dist/src \
		${NETBSDSRCDIR}/external/mit/lua/dist/doc

.include <bsd.prog.mk>
