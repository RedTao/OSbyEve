
# 默认动作

default :
	../z_tools/make.exe img

# 镜像文件生成

boot.bin : boot.nas Makefile
	../z_tools/nask.exe boot.nas boot.bin boot.lst

helloos.img : boot.bin Makefile
	../z_tools/edimg.exe   imgin:../z_tools/fdimg0at.tek \
		wbinimg src:boot.bin len:512 from:0 to:0   imgout:helloos.img

# 其他指令

asm :
	../z_tools/make.exe -r boot.bin

img :
	../z_tools/make.exe -r helloos.img

run :
	../z_tools/make.exe img
	copy helloos.img ..\z_tools\qemu\fdimage0.bin
	../z_tools/make.exe -C ../z_tools/qemu

install :
	../z_tools/make.exe img
	../z_tools/imgtol.com w a: helloos.img

clean :
	-del boot.bin
	-del boot.lst

src_only :
	../z_tools/make.exe clean
	-del helloos.img
