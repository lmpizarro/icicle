# Icicle en EDU-FPGA

Instrucciones específicas para [EDU-FPGA](http://www.proyecto-ciaa.com.ar/devwiki/doku.php?id=desarrollo%3Aedu-fpga):

## Instalación nativa de las herramientas

Estos pasos fueron probados con `Linux Mint 20 Cinnamon` en un sistema de 64-bits `x86_64`.

### Prerrequisitos

- Crear un directorio de trabajo y posicionarse en él.
```
mkdir -p ~/edufpga-icicle/
cd ~/edufpga-icicle/
```

- Instalar herramientas disponibles en el repositorio (`make`, `vim`, `arachne-pnr` y `icestorm`, entre otras necesarias para construir las herramientas).

```
sudo apt update
sudo apt install git make arachne-pnr fpga-icestorm vim autoconf automake autotools-dev curl python3 libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev gtkterm
```

### Toolchain RISC-V

Clonar y construir el toolchain para `RV32I`. La instalación necesita privilegios de root.

**NOTA**: Este repositorio es grande (~7GB). Clonarlo y luego construirlo lleva tiempo, ¡paciencia!

```
cd ~/edufpga-icicle/
git clone --recursive https://github.com/riscv/riscv-gnu-toolchain
cd riscv-gnu-toolchain

./configure --prefix=/opt/riscv --with-arch=rv32gc --with-abi=ilp32d
sudo make # compila e instala
```

### Icarus Verilog

### Arachne-pnr

### IceStorm

### Vim

### Yosys


## Uso de las herramientas mediante dockers

A definir.

## Generación del bitstream

- Asegurar que el compilador esté disponible en `PATH`:
```
export PATH=/opt/riscv/bin/:$PATH
```
Así el comando `riscv32-unknown-elf-gcc` debería ser accesible.
