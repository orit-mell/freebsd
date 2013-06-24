# $FreeBSD: release/9.1.0/sys/modules/mlx4ib/Makefile 219820 2011-03-21 09:58:24Z jeff $
.PATH:  ${.CURDIR}/../../ofed/drivers/infiniband/hw/mlx4

.include <bsd.own.mk>

KMOD    = mlx4ib
SRCS    = device_if.h bus_if.h pci_if.h vnode_if.h opt_inet.h opt_inet6.h
SRCS+=	ah.c cq.c doorbell.c mad.c main.c mr.c qp.c srq.c wc.c
SRCS+=	opt_inet.h opt_inet6.h

CFLAGS+= -I${.CURDIR}/../../ofed/include/

.if !defined(KERNBUILDDIR)
.if ${MK_INET_SUPPORT} != "no"
opt_inet.h:
	@echo "#define INET 1" > ${.TARGET}
.endif

.if ${MK_INET6_SUPPORT} != "no"
opt_inet6.h:
	@echo "#define INET6 1" > ${.TARGET}
.endif
.endif

.include <bsd.kmod.mk>

CFLAGS+= -Wno-cast-qual -Wno-pointer-arith -fms-extensions
