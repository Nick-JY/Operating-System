# xv6

## 1.QEMU

- 通俗点来讲，**QEMU**是一款**开源的虚拟机**。

  - 虚拟机的作用就是作为**仿真器**(Emulator)，仿真各种体系结构(CPU)。

  - **QEMU**支持如下体系结构的仿真：

    - **i386架构**：
      - 英特尔于1985年推出的**32位**指令集架构，又被称为**x86架构**或**IA-32架构**，是**8086架构**(16位)的延伸版本，首次应用在**Intel 80386**芯片中。
    - **x64架构**：
      - **x64架构**是**x86架构**的**64位**拓展，因此也叫**x86-64架构**。
      - AMD于1999年推出**x64架构**，并且向英特尔公开，因此也叫**amd64架构**。
      - 该架构从**Pentium 4**开始，一直应用到现在的高端处理器。
    - **MIPS64架构**：
      - 精简指令集架构，开源指令集架构，由美国的MIPS公司研制，**MIPS架构**的学习多出现在计算机体系结构的课程上。
      - 2021年，**MIPS架构**停止开发，MIPS公司正在想**RISC-V架构**过渡。

    - **ARM架构**：
      - **ARM**的架构就非常多了......

    - **PowerPC**架构：
      - 精简指令集架构，由Apple、IBM、Motorola组成的**AIM联盟**设计，源自IBM的**Power架构**。
      - **PowerPC 601**：
        - 第一个Power PC架构的处理器。
      - **PowerPC架构**大多被Apple使用，2005年之后，Apple不再使用**PowerPC架构**，转向**x86-64**架构。

    - **RISC-V架构**：
      - 精简指令集架构，开源指令集架构，**RISC-V架构**代表着"**开源硬件运动**"，该运动于2010年在加州大学伯克利分校启动。

- **QEMU**所模拟的**体系架构**由纯软件实现，并在**Guest OS**与**Host OS**中间，来处理**Guest OS**的硬件请求，并由**QEMU**转译给真正的硬件。

## 2.xv6：

- **xv6**是用**ANSI C**重新编写的**Unix第六版**(Version 6 Unix，1975年发行)现代实现版本，适用于**i386架构**和**RISC-V架构**。

- **xv6**于2006年问世，作为MIT的操作系统工程(6.828)课程的教学使用。

- **xv6—i386架构**的版本于2020年停止更新，**xv6—RISC-V架构**的版本依旧在更新。

  - GitHub仓库：https://github.com/mit-pdos/xv6-riscv

- **xv6—中文文档仓库**：

  - [xv6中文文档](https://th0ar.gitbooks.io/xv6-chinese/content/)

- 在**Ubuntu22.04**上构建**xv6**环境：

  - 构建配置工具链：

    - ```shell
      sudo apt-get install git build-essential gdb-multiarch qemu-system-misc gcc-riscv64-linux-gnu binutils-riscv64-linux-gnu
      ```

  - 拉取[xv6-riscv](https://github.com/mit-pdos/xv6-riscv)仓库：

    - ```shell
      git clone git@github.com:mit-pdos/xv6-riscv.git
      ```

  - 进入本地仓库：

    - ```shell
      cd xv6-riscv
      ```

  - 构建xv6环境：

    - ```shell
      make qemu
      ```

- **xv6**的使用：
  - 进入xv6系统：
    - 在`xv6-riscv`目录下执行`make qemu`。
  - 退出xv6系统：
    - `ctrl + a + c`进入**qemu**界面。
    - 在**qemu**界面，使用**q**退回到**shell**。