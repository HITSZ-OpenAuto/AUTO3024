# AUTO3024 - 嵌入式系统


![考查课](https://img.shields.io/badge/%E8%80%83%E6%9F%A5%E8%AF%BE-green)
![学分](https://img.shields.io/badge/%E5%AD%A6%E5%88%86-2-moccasin)

![成绩构成](https://img.shields.io/badge/%E6%88%90%E7%BB%A9%E6%9E%84%E6%88%90-gold)
![作业10%](https://img.shields.io/badge/%E4%BD%9C%E4%B8%9A-10%25-wheat)
![实验50%](https://img.shields.io/badge/实验-50%25-wheat)
![期末考试40%](https://img.shields.io/badge/%E6%9C%9F%E6%9C%AB%E8%80%83%E8%AF%95-40%25-wheat)

本课程是将《自动控制实践 B》中嵌入式（STM32）部分独立出来，从22级开始开设。部分考试资料可以去 [自动控制实践 B](https://hoa.moe/docs/junior-spring/auto3002b/) 的页面下载。

## 教材与参考书

- 教材：课程 ppt、实验指导书。
- 参考资料：
  - [南工骁鹰嵌入式软件培训](https://www.bilibili.com/video/BV1VT411N7dK)，某学长锐评：真想学 STM32 还是它的含金量高。包含了许多本课程中未包含的内容（CAN等）。


## 授课教师

- 理论课：黄瑞宁
  - 这位老师参与过18、19级学生的《自动控制实践 B》教学，彼时他就负责其中嵌入式部分的讲授。后来由于不明原因不再讲授该课程，现在复出。
  - 授课风格：
    - 同学 1：偶尔考勤，上课细致。
    - 同学 2：若无基础较难听懂。
- 王彬彬
  - 人很好，一直帮忙解决问题，多问老师，和同学多交流可以实验满分。但是基本上大家都没有在安排的实验课内完成，大部分同学都是课下去做完的。最后实验老师会给没做出的同学讲解代码。

> 文 / [Oliver Wu](https://github.com/oliverwu515) 根据 zhou & hyq 的描述整理, 2025.1

## 学时安排

理论课共20学时，内容详见 osa 网盘中的 ppt。

主要分为：嵌入式系统概述；CubeMX 配置与 Keil 编程环境；GPIO；中断【中断及复位启动，中断优先级及配置（嵌套中断向量控制机制）、中断服务函数、外部中断/事件控制器】；串口与 DMA；AD/DA；定时器【systick 定时器、基本定时器、通用定时器；定时器的特殊模式：输入捕获、输出比较等功能】；高级定时器【编码器接口、霍尔传感器接口……】。

实验课共 12 学时：

共设置基础实验 12 个（共 8 学时，每 2 个学时完成 3 个实验），难度不大，具体内容见「资料下载」中的实验指导书。在基础实验里，记得把 SYS 中的 Debug 设置成 JTAG(4pins)，指导书里没提这一点。

{{% details title="基础实验内容" closed="true" %}}

1. 单个LED闪烁实验（GPIO）
2. LED流水灯实验（GPIO）
3. 按键控制LED实验（GPIO）
4. 外部中断实验（EXTI）
5. 定时器定时应用实验（TIM）
6. DAC 基本实验
7. TFT 屏基本实验
8. 串行通讯基本实验（UART）
9. DMA 直接内存访问实验 
10. DMA-UART 收发实验 
11. ADC 采集实验
12. AD 转换及定时器 PWM 输出实验

{{% /details %}}

基础实验完成后是电机控制调速实验（共4学时，相比于原先的8学时有了大幅度的压缩，难度也随之增大，所以请提前写好代码。之前基础实验中部分代码可以复用）。具体内容可以参考「资料下载」中的实验指导书。

> 文 / [Oliver Wu](https://github.com/oliverwu515)，2024.7

## 关于考试

考试题型大概是四个选择（每题5分）外加8-10个简答和简单计算，除选择题外基本上见于 `materials/2024-嵌入式复习.pptx`。给分很高。

> 文 / [Oliver Wu](https://github.com/oliverwu515) 根据 zhou & hyq 的描述整理, 2025.1

## 学习建议

实验课的内容是 STM32 开发，实验涵盖了：GPIO、外部中断、串口通信、DMA 等功能的上手。开发板的 MCU 型号是 STM32F407ZGT6，软件是 MDK v5 + CubeMX。

实验软件所使用的 CubeMX 是 STM32Cube —— 目前 STM32 最主流的开发方式的重要一环。而2019年推出的 STM32CubeIDE，则是这个生态系统的集大成者。

与 MDK 不同的是，STM32CubeIDE 还提供对 MacOS 或者 Linux 操作系统的支持。我非常推荐大家使用 STM32CubeIDE 这个 All in one 的软件（包含了 CubeMX，可以不用单独下载）进行使用。

以下是一些有用的链接：

- [STM32StepByStep:Step2 Blink LED](https://wiki.stmicroelectronics.cn/stm32mcu/wiki/STM32StepByStep:Step2_Blink_LED)：通过点灯，快速熟悉 IDE 的开发流程。
- [CH341 串口驱动](https://www.wch-ic.com/downloads/CH341SER_EXE.html)：除了老师一般会发的 Windows 版本外，还含有 MacOS 和 Linux 的版本。
- [printf 重定向](https://github.com/STMicroelectronics/STM32CubeH7/blob/master/Projects/STM32H743I-EVAL/Examples/UART/UART_Printf/Src/main.c): STM32 官方文档中的重定向方法。

> 文 / [Kowyo](https://github.com/kowyo)，2024.6
