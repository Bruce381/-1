# **大综合1**
| 版本 | 链接 |
| ---- | ---- |
| English 关键词版本 | [跳转到页面](English.md) |
|Normal English | [跳转到页面](for_recitation.md) |



## **计算机系统原理(Computer System Fundamentals)**
- EEPROM (Electrically Erasable Programmable read only memory) 
  - 用途和特性
    - EEPROM 是一种**带电可擦可编程只读存储器**，掉电后数据不丢失。可以擦除已有信息并重新编程，广泛用于即插即用设备，如 U 盘。

    - 用途
      - 数据存储：保存用户设定、设备参数等小型非易失性数据。
      - 配置存储：嵌入式系统中存储固件或硬件配置信息。
      - 固件更新：部分设备用于存储可更新的代码或校准数据。
    - 特性
      - 非易失性：断电后数据不会丢失。
      - 可擦写：电气方式多次擦写，但有擦写寿命（通常 10,000～1,000,000 次）。
      - 字节级操作：支持逐字节读写，灵活性高。
      - 慢速写入：写入速度比读取慢。
- RAM
  - 静态RAM (SRAM) 和动态RAM (DRAM) 比较
    - DRAM 则适合主存，强调容量和成；SRAM 适合高速缓存，强调速度；

        | **Characteristic** | **DRAM** | **SRAM** |
        |--------------------|----------|----------------|
        | **Storage** | **Capacitance**(电容) & **Transistor**（晶体管） | **Transistor**（晶体管） |
        | **Refresh**    | **refresh regularly** （定期刷新）| **Not refresh** |
        | **Speed**        | Slow    | Fast   |
        | **Power**        | High  | Low |
        | **Density**（密度）| High |Low |
        | **Cost**        | Low    | High  |
        | **Apply**        | Memory | CPU,GPU |

    - 主存和缓存的功能与使用
      - 主存（RAM）
        - **功能**：存储当前运行的程序和数据，支持多任务处理。
        - **使用**：操作系统和应用程序在主存中加载并执行指令，存储正在使用的数据。
      - 缓存（Cache）
        - **功能**：加速CPU对主存中数据的访问。存储热点数据，减少访问延迟。
        - **使用**：CPU通过缓存提高对数据的访问速度，减少从主存读取的次数。
      - 主存 vs 缓存
        | 特性 | 主存（RAM） | 缓存（Cache） |
        | ---- | --------- | ------------ |
        | 速度 | 较慢 | 非常快 |
        | 目的 | 存储程序和数据 | 加速CPU访问数据 |
        | 访问方式 | 由CPU或其他硬件直接访问 | CPU自动管理缓存内容，通常透明给应用程序 |
        | 成本 | 较低 | 较高 |
- 虚拟内存 (Virtual Memory) (Swap)
  - **定义和系统中角色**：虚拟内存是操作系统用来扩展物理内存的一种技术，通常通过硬盘的交换空间来实现。

- 总线系统
  - 地址总线
    - **用途**：传输内存地址，作用是存取数据，通常是单向。
  - 数据总线
    - **用途**：传输数据，支持双向通信。通过32位或64位数据总线来提升系统运行速度。
  - 控制总线
    - **作用**：传递控制信号，协调计算机系统各部件的工作。
      - **时钟信号线**（Clock Signal Line）: 
        - 概念：
          - Clock Signal Line 是电子电路中用于同步各个组件、确保数据传输按时序进行的信号线。时钟信号通常是一个周期性的波形，用来为系统中的各个部件提供统一的时间基准。时钟信号的作用类似于一个指挥官，指示每个操作应何时执行。
          - 周期性信号: 时钟信号是一种周期性变化的方波信号，其周期决定了信号的频率。频率越高，时钟周期越短，系统能够进行的操作就越多。
          - 同步信号: 时钟信号用于同步计算机系统中各个部件（如 CPU、内存、外设等）之间的工作。所有的同步操作通常都基于时钟信号的上升沿或下降沿。
          - 时钟周期: 时钟信号的一个完整周期通常包含一个上升沿和一个下降沿（方波信号）。每个时钟周期内，电路中的寄存器、计算单元等会根据时钟信号的变化做出相应的反应。
      
        - 作用：
          - 同步时序：时钟信号确保系统中的各个部件在同一时间步调下工作。例如，CPU、内存和其他外设的操作需要在相同的时钟周期下同步进行。

          - 数据传输：在数据传输过程中，时钟信号作为数据的同步基准。数据在时钟信号的控制下按照一定的时序进行传输。例如，在串行和并行数据通信中，时钟信号决定了数据的发送和接收时机。

          - 定时控制：时钟信号可以用作定时控制器，在特定的时刻控制某些操作的执行。比如，CPU 内部的运算和控制周期，内存的读写等都依赖时钟信号来保证按时执行。

          - 触发器和寄存器的工作：许多数字电路，尤其是触发器（如 D 触发器）和寄存器，都是基于时钟信号来存储和更新数据的。只有在时钟的特定边沿（上升沿或下降沿）触发时，寄存器才会更新其值。
      
        - 类型：
          - 全局时钟（Global Clock）：全局时钟信号是系统中所有部件共同使用的时钟信号，通常由时钟源（如晶体振荡器）生成。所有同步操作都是基于这个全局时钟信号进行的。

          - 局部时钟（Local Clock）：局部时钟信号通常在某些特定的模块或组件中使用，例如特定的外设或处理单元可能会有独立的时钟源。局部时钟可能与全局时钟不同，或是由全局时钟分频生成。
          - 同步时钟与异步时钟：
            - 同步时钟：系统的所有模块共享同一时钟源，所有部件的操作都基于统一的时钟信号同步执行。
            - 异步时钟：不同模块或部件使用不同的时钟信号，它们的操作不一定完全同步，可能导致时钟同步问题，需要采用额外的同步机制来解决。
      
      - **中断请求线**(Interrupt Request Line)：
        - 概念
          - Interrupt Request Line，简称 IRQ）是计算机硬件系统中用于处理外部或内部事件的信号线。当某个外部设备或系统内部出现需要处理的事件时，该设备或系统通过中断请求线向处理器发出信号，要求CPU暂停当前的操作，转而处理该事件。中断机制使得计算机系统能够响应外部和内部事件，而不需要轮询或忙等待，从而提高效率。
          - 中断请求（IRQ）：中断请求是指由外部硬件设备（如键盘、鼠标、硬盘等）或内部事件（如定时器、程序错误等）触发的信号，要求CPU中断当前任务并执行与该事件相关的处理程序。

          - 中断线（IRQ Line）：中断请求线是一条物理信号线，通常连接到处理器的中断控制器。每条中断请求线对应一个中断源（如设备或系统事件）。处理器通过中断控制器判断哪个中断请求需要优先处理。

          - 优先级：中断请求线通常有优先级的概念。不同的中断请求源根据系统设计会有不同的优先级。处理器会根据中断的优先级决定处理中断的顺序。

          - 中断控制器：中断控制器（如 PIC 或 APIC）是负责管理中断请求的硬件组件。它负责接收来自各个设备的中断请求信号，并根据预定的优先级规则，将中断请求传递给 CPU。
        
        - 工作:
          - 事件发生：外部设备或系统内部事件发生时，会向中断控制器发出中断请求。例如，当硬盘有新的数据可读时，硬盘控制器会发出中断请求，通知 CPU 处理数据。

          - 中断信号传递：中断请求信号通过中断请求线传递到处理器。中断控制器接收到多个请求后，会根据请求的优先级来决定哪个请求应当优先处理。

          - 中断识别和处理中断：CPU 在执行完当前指令后，会检查是否有中断请求。如果有中断请求，CPU 会暂停当前操作，将控制权交给中断处理程序（通常称为中断服务例程，ISR）。中断服务程序执行完毕后，CPU 会恢复原来的任务。

          - 中断结束：中断处理完毕后，CPU 会通过恢复程序的执行状态，继续原来的任务。
        
        - 分类：
          - 硬件中断（Hardware Interrupt）：硬件中断是由外部设备产生的中断请求，例如键盘输入、鼠标点击、硬盘I/O等。硬件设备通过中断请求线将中断信号发送到处理器，请求其处理数据。

          - 软件中断（Software Interrupt）：软件中断是由程序代码发出的中断信号。程序执行时，如果遇到特定的指令（如 int 指令），会触发一个软件中断，通知操作系统或处理器进行特定操作。

        - 类型：
          - 标准中断请求线（IRQx）：在传统的计算机系统中，常见的中断请求线通常命名为 IRQ0 到 IRQ15。每一条中断请求线对应一个特定的硬件设备或事件。
          - PCI 中断请求线：在基于 PCI（Peripheral Component Interconnect）的系统中，设备通过独立的中断请求线与主板上的中断控制器进行通信。现代系统中使用的 PCI、PCIe 总线通常提供多个中断请求线，允许多个外设同时请求中断。
          - APIC 中断请求：在更复杂的系统（如多核处理器和高端服务器）中，使用了 APIC（Advanced Programmable Interrupt Controller）来管理和分配中断。APIC 支持更高效的中断分配和优先级管理。
        - 优先级与管理:
          - 优先级排序：中断请求线通常有不同的优先级，低优先级的中断可以被高优先级的中断“抢占”。例如，硬件设备的中断可能比一些常规的系统任务具有更高的优先级。

          - 中断嵌套（Interrupt Nesting）：在中断处理中，可能会发生更高优先级的中断打断低优先级中断的情况，形成中断嵌套。现代 CPU 通常能够处理多级中断，并允许某些中断打断正在执行的其他中断。

          - 中断屏蔽：通过中断屏蔽寄存器（Interrupt Mask Register，IMR），操作系统或硬件可以选择屏蔽某些中断请求，使其暂时不响应。这在某些情况下是必要的，比如在处理某些关键任务时，需要屏蔽低优先级的中断。

          - 中断向量：每个中断请求源都有一个中断向量，这个向量是一个指向中断服务例程（ISR）的指针。当中断发生时，CPU 会根据中断请求的类型（通过 IRQ 线）跳转到相应的中断向量，执行对应的 ISR。
         
      - **读/写控制线**（Read/Write Control Lines）：
        - 概念：
          - Read/Write Control Lines 是计算机和数字系统中用于控制数据传输方向和操作类型的信号线。它们在总线系统中发挥着关键作用，帮助系统区分何时进行数据的读取（读取操作）和写入（写入操作）。通常，读/写控制线是 CPU 与内存、外设等组件之间的通信协议的一部分。
        - 操作：当需要从存储设备（如内存、硬盘等）读取数据时，控制线会发送一个读信号（通常标记为 READ 或 RD），指示系统准备从指定的地址获取数据。

        - 写操作：当需要将数据写入存储设备时，控制线会发送一个写信号（通常标记为 WRITE 或 WR），指示系统将数据写入到指定的地址。
      
      - 作用：
        - 控制数据传输方向：读/写控制线的主要作用是控制数据流的方向。通过设置读或写信号，系统能够确定数据是从外设或内存读取（读操作）还是写入外设或内存（写操作）。

        - 确定操作类型：读/写控制线帮助定义当前总线操作的类型。当系统正在进行数据交换时，读信号或写信号可以帮助各个组件知道该执行何种操作。

        - 同步通信：在总线协议中，读/写控制线通常与时钟信号、地址信号以及数据总线的控制信号一起工作，保证所有的数据交换按照时序进行，以确保可靠的同步操作。

        - 选择器信号：有时，读/写控制信号还作为其他设备或模块的选择信号，指示哪个设备或存储器正在进行当前的操作。
      
      - **存储器使能线**（Memory Enable Line）:
        - 是用于控制存储器访问的信号线。它决定了存储器模块是否被选中，以响应读/写操作。
      - **I/O端口使能线**（I/O Port Enable Line）:
        - 用于控制 I/O 设备的访问。它决定特定的 I/O 端口是否被激活，以进行数据读写操作。
      - **NMI（不可屏蔽中断）**
        - **作用**：用于处理紧急事件或硬件故障，无法被屏蔽，确保紧急情况得到优先响应。
        - 特点:
          - 不可屏蔽:NMI 是不可被屏蔽的，即使操作系统或程序通过设置中断屏蔽寄存器（如 CPU 的中断屏蔽标志）来忽略其他中断，NMI 仍然会被处理
          - 高优先级:NMI 通常用于处理紧急且需要立即响应的事件，其优先级高于其他大多数中断。
          - 用于硬件故障检测:NMI 多用于硬件级别的错误通知，如内存故障、温度过高、硬件故障、或 CPU 本身的错误等。这些错误通常需要立即修复或处理，以防系统进一步损坏或数据丢失。
          - 用于调试:在一些系统中，NMI 也被用作调试工具，当程序发生严重错误时，可以触发 NMI 中断来中断当前执行的程序，进入调试模式。
            
        - 触发方式: NMI 主要是由硬件触发的
          - 硬件故障：例如，CPU 检测到某些硬件故障（如内存错误、芯片过热等），会生成 NMI。
          - 定时器：某些系统在特定时间间隔后产生 NMI，用于健康检查或维护任务。
          - 外部事件：例如，某些系统组件或外部设备触发 NMI 以通知操作系统紧急事件。
        - 应用：
          - 硬件错误监控：NMI 常常用于检测硬件故障，例如内存错误、磁盘故障、或其他系统级硬件问题。操作系统接收到 NMI 信号后，可以启动紧急处理程序，记录错误日志，进行故障转储，甚至可以重启系统。
          - 系统维护：在一些嵌入式系统中，NMI 用于监控系统状态，如温度过高或电压异常等。若系统检测到不正常情况，就会通过 NMI 中断发出警告。
          - 调试和故障排查：在开发和调试阶段，硬件系统可能会通过 NMI 进入调试模式。开发者可以通过捕获 NMI 来检查系统状态或进行硬件的状态调试。
          - 实时操作系统和安全性：某些实时操作系统（RTOS）和高安全性要求的系统，会利用 NMI 来确保关键任务的及时处理，即使在系统负荷较重的情况下，也能优先处理一些重要任务。
        
        - 处理步骤：当 NMI 发生时，操作系统内核会接管并中断当前的任务。
          - 保存上下文：首先，系统会保存当前任务的上下文（如寄存器状态），以便处理完 NMI 后能够恢复。
          - 处理中断：操作系统会运行一个专门处理 NMI 的中断服务程序。这个服务程序会根据 NMI 的原因执行适当的动作。
          - 恢复操作：一旦 NMI 处理完毕，系统会恢复到原来的状态，继续执行之前被中断的任务。

- 真值表 !!!
  - **用于描述逻辑电路的输入与输出关系。**

      | A | B | C | A and B | A or C | not B | (A and B) or (not B) |
      |---|---|---|---------|--------|-------|----------------------|
      | 0 | 0 | 0 |    0    |   0    |   1   |          1           |
      | 0 | 0 | 1 |    0    |   1    |   1   |          1           |
      | 0 | 1 | 0 |    0    |   0    |   0   |          0           |
      | 0 | 1 | 1 |    0    |   1    |   0   |          0           |
      | 1 | 0 | 0 |    0    |   1    |   1   |          1           |

## 系统软件与工具
- **实用程序软件**
  - **作用**：
    - 增强操作系统的功能，例如资源管理器、磁盘碎片整理等。
      - 磁盘清理：帮助清理硬盘上的临时文件、缓存和不必要的文件，以释放存储空间并提高系统性能。
      - 磁盘碎片整理：对硬盘上的文件进行重新排序，减少数据访问的延迟，从而提高计算机的读取速度。
  - 例子：
    - 系统清理工具（如CCleaner）
    - 压缩解压工具（如WinRAR、7-Zip）
    - 备份与恢复工具（如Acronis True Image）
    - 磁盘管理工具（如Partition Wizard）
    - 防病毒与安全工具（如Malwarebytes）
    - 文件管理工具（如Total Commander）
    - 网络工具（如Wireshark）
    - 驱动更新工具（如Driver Booster）
 
- **备份与恢复**
  - **完整备份的作用和文件属性变化**：
    
    - 增量备份、完全备份、差异备份
      - 完全备份（Full Backup）：是指对所有选定的文件和数据进行完整备份，通常是一个初始备份。每次执行完整备份时，备份的数据都是完整的，不依赖任何之前的备份。
        - 优点：恢复过程简单、快捷，因为数据是完整的。
        - 缺点：占用存储空间较多，并且备份时间较长。
      
      - 增量备份（Incremental Backup）：只备份自上次备份以来发生变化的文件。增量备份通常依赖于上一次备份的结果，只有更改过的文件会被备份。
        - 优点：备份速度快，占用空间小。
        - 缺点：恢复过程较复杂，因为恢复时需要使用最后的完全备份和所有增量备份。
      
      - 差异备份（Differential Backup）：备份自上一次完全备份以来发生变化的所有文件。每次差异备份都会备份自上次完全备份以来的所有更改文件。
        - 优点：比增量备份的恢复过程简单，但比完全备份的恢复过程慢。
        - 缺点：随着备份次数的增加，差异备份占用的空间会逐渐增大。
      
      - Archive Flag:
        
        - 归档标志是文件系统中的一种属性，它通常用于指示文件自上次备份以来是否已发生更改。操作系统通过该标志帮助备份工具识别哪些文件是新的或被修改的，以便进行增量或差异备份。
        
        - 步骤:
          - 设置归档标志：当文件内容被修改时，操作系统会自动设置归档标志（在文件系统中将此属性设置为“启用”），表示该文件自上次备份以来已更改。
          
          - 备份时的作用：备份程序在执行增量备份或差异备份时，会检查文件的归档标志。如果标志为“启用”，则表示该文件自上次备份以来已被修改，备份程序将其包括在备份中。
  
          - 归档标志重置：当备份程序执行完备份后，会将归档标志重置为“禁用”，表示该文件已经被备份过了。对于增量备份和差异备份，重置归档标志是非常重要的步骤。

## 软件开发导论
- 基本编程概念
  - 变量类型
    - 整数、字符、字符串、实数（小数包含在这里）

  - 编程结构
    - 顺序、选择、迭代

  - 函数
    - 内置函数和自定义函数的使用：
      - 降低复杂度，代码清晰，代码复用，提高可维护性。
    - 参数传递与返回值：
      - 传递值参与运算，返回值使得下一个函数可以继续运算。
      - 按值传递、按引用传递、按名称传递。

- 编程实践
  - 良好的编程习惯
    - 变量命名：有意义的变量名。
    - 代码注释：让接手的人看懂，提醒自己。
    - 使用空白控件(缩进)：提高代码可读性。
  - 局部变量和全局变量
    - 作用和作用域：局部变量仅在函数内有效，全局变量在整个程序中有效。
  - 白盒测试（white box testing）
    - 适用性和方法：测试代码内部逻辑。（只有专业计算机人员才能胜任）
  - 黑盒测试
  
- 数据处理
  - 处理有效和无效输入
    - 设计健壮的输入验证机制
- 故障排除和测试
  - 错误识别和解决策略：识别错误、制定策略、执行步骤。
- 技术手册的编写
  - 手册的主要部分
    1. 需求规格
    2. 详细设计
    3. 代码清单
    4. 测试策略
    5. 测试日志

    - 找bug从上到下排除

- 伪代码找出bug
  - 通过伪代码分析来识别潜在的bug
    ```
    Initialize total to 0
    Set array to [3, 5, 2, 8, 7, 10, 12]
    Set length to the number of elements array
    Initialize index to 0
    Loop while index is less then length
        If array[index] mod 2 equals 0 then
            Set square to array[index] * array[index]
            Add square to total
        End If
        Increment index by 1
    End Loop
    Display total
    ```

## 职业道德 (Professionalism and Ethics in Computing)  只需要了解
- 法律与法规（英国为主）
  - 版权，设计和专利法
    - 知识产权保护的基本原则
      1. 激励创新：通过法律保护创造者权益，激励技术进步和文化发展。
      2. 公平竞争：维护市场秩序，防止侵权和不正当竞争。
      3. 平衡利益：保护权利人与公众之间的利益平衡，促进知识传播和社会进步。
      4. 地域性原则：知识产权的保护具有地域限制，适用各国法律。
      5. 时间性原则：保护有时效，超过期限进入公共领域。
      6. 法律优先：通过法律手段解决侵权争议，保障合法权益。
  - 数据保护法
    - 个人数据处理和储存的法律要求
      1. 数据收集需合法、透明，并取得用户同意。
      2. 数据仅限于特定目的，不得滥用或超范围使用。
      3. 实施技术和组织措施，确保数据安全与隐私保护。
    - 数据保留和数据准确性的重要性
      1. 数据保留：仅在必要时间内存储数据，超期应安全删除。
      2. 数据准确性：确保数据完整、最新，避免误导或错误影响决策。
  - 消费者保护法
    - 电子商务中的消费者权利和公司的义务
        1. 知情权：消费者有权了解商品信息、价格、退换政策等。
        2. 选择权：自由选择商品或服务，无强制消费。
        3. 安全权：享有购买安全合规商品的保障。
        4. 隐私权：个人数据受法律保护，不得非法收集或滥用。
        5. 售后权：享有合理退换货及售后服务的保障。
        6. 提供清晰、准确的信息，杜绝虚假宣传。
        7. 确保支付安全，保护消费者个人信息。
        8. 履行合同，及时发货并提供售后服务。
        9. 遵守退换货政策，按承诺解决纠纷。

- 职业道德与行为
  - 职业协会与认证
    - 例如 BCS （加入之后他们可以提供什么优势和服务）
      1. 专业网络：拓展行业人脉，与同行交流合作。
      2. 技能提升：提供培训、研讨会和持续教育机会。
      3. 行业资源：获取最新趋势、研究报告和工具支持。
      4. 职业认证：提升专业形象和就业竞争力。
      5. 政策影响：参与行业标准制定，增强话语权。
      6. 求职支持：提供招聘信息、职业指导和推荐机会。
  
  - 职业行为守则
    - 专业机构的成员应按照专业机构的规定行事
    - 要求
      - 专业机构成员需遵守诚信、公正、保密等原则。
      - 遵循专业机构的规定，维护行业声誉与标准。
      - 遇到利益冲突时，优先保护客户和公众利益。

  - 使用政策和安全
    - 可接受使用政策(Acceptable use policy.AUP)和计算机硬件软件的安全管理
      - 可接受使用政策 (AUP)
        1. 明确用户在使用组织资源（网络、设备等）时的行为准则。
        2. 禁止非法、滥用或未经授权的使用行为。
        
      - 计算机硬件软件的安全管理
        1. 定期更新与补丁，防范安全漏洞。
        2. 实施访问控制，确保权限分配合理。
        3. 数据备份与加密，防止信息泄露或丢失。

- 计算机领域职业及机构 
  - 职业
    - 软件开发工程师 (Software Development Engineer) 科技公司，金融机构，电商平台，初创公司
    - 数据库管理员 (DBA很赚钱) (Database Administrator) 银行，数据密集型企业，云服务提供商，政府部门和高校
    - 系统架构师 (Systems Archtect) 企业IT部门，IT咨询公司？，云计算和AI公司
  - 机构
    - 英国应用软件开发者协会
    - 国际电器与电子工程师协会
    - 美国计算机学会
- 计算机犯罪
  - 未授权的软件复制
    - 法律后果和公司策略
      - 法律后果
        1. 侵犯版权，可能面临罚款、刑事诉讼或赔偿责任。
        2. 企业可能失去信任，影响声誉和合作关系。
      - 公司策略
        1. 制定并实施软件许可合规政策。
        2. 定期审计软件使用，禁止盗版。
        3. 提供合法软件和员工培训。
  - 安全与保密性
    - 处理敏感数据防止数据泄露方法
      - 数据加密：传输与存储时加密保护。
      - 访问控制：限制敏感数据的访问权限。
      - 定期备份：防止数据丢失或篡改。
      - 网络安全措施：使用防火墙、反病毒软件等保护系统。
      - 员工培训：提高安全意识，防范钓鱼攻击和内部泄露。

# 故障诊断
- 常见系统问提
  - 系统性能问题 (System Performance Issues)
    - 磁盘碎片整理、交换文件调整、进程管理
      - 磁盘碎片整理：优化磁盘数据存储，提升读取速度。
      - 交换文件调整：根据内存需求配置适当大小的虚拟内存。
      - 进程管理：终止无响应或占用资源过多的进程。
  - 软件和硬件问题 (Software and Hardware Issues)
    - 识别和解决硬件故障和软件错误的方法.
      - 硬件故障：检测电源、连接线、硬件组件是否损坏。
      - 软件错误：检查日志，更新补丁，恢复至稳定版本。
- 文档编写 (Documentation)
  - 问题调查阶段 (Investigation Stage)
    - 问题描述、症状记录和初步诊断
      - 问题描述：记录问题发生的时间、范围及影响。
      - 症状记录：收集错误信息、用户反馈和日志文件。
      - 初步诊断：定位问题可能的原因和涉及的系统模块。
  - 解决方案阶段 (Solution Stage)
    - 解决步骤、实施策略和变更记录
      - 解决步骤：列出详细的操作步骤和修复方案。
      - 实施策略：制定最小化风险的实施计划。
      - 变更记录：记录变更内容和时间以备后续跟踪。
  - 测试阶段 (Testing Stage)
    - 测试用例、结果记录和重新测试的必要性
      - 测试用例：设计验证问题是否解决的具体用例。
      - 结果记录：记录测试结果，判断问题是否彻底解决。
      - 重新测试：在必要时多次测试以确保系统稳定性。
