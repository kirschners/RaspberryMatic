obj-m += generic_raw_uart.o
ifeq ($(CONFIG_ARCH_BCM2835),y)
  obj-m += pl011_raw_uart.o
else
  obj-m += dw_apb_raw_uart.o
endif

ifeq ($(KERNELRELEASE),)
  KERNELRELEASE := $(shell uname -r)
endif

ifeq ($(KERNEL_DIR),)
  KERNEL_DIR := /lib/modules/$(KERNELRELEASE)/build
endif

all:
	$(MAKE) -C $(KERNEL_DIR) M=$(PWD) modules

clean:
	$(MAKE) -C $(KERNEL_DIR) M=$(PWD) clean

