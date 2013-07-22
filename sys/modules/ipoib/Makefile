# $FreeBSD$
.PATH:  ${.CURDIR}/../../ofed/drivers/infiniband/ulp/ipoib
.PATH:  ${.CURDIR}/../../ofed/include/linux

.include <bsd.own.mk>

KMOD    = ipoib
SRCS    = ipoib_cm.c ipoib_ib.c ipoib_main.c ipoib_multicast.c ipoib_verbs.c ipoib.h
SRCS+=  linux_compat.c linux_radix.c linux_idr.c

CFLAGS+= -I${.CURDIR}/../../ofed/drivers/infiniband/ulp/ipoib
CFLAGS+= -I${.CURDIR}/../ibcore
CFLAGS+= -I${.CURDIR}/../../ofed/include/

.include <bsd.kmod.mk>

CFLAGS+= -Wno-cast-qual -Wno-pointer-arith -fms-extensions
