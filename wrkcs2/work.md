# Work-case №2
## Виконав Харечко 

## Glossary

* Virtual Machine (VM) – A software emulation of a physical computer, allowing operating systems and applications to run in an isolated environment away from the main host machine.
* Type 2 Hypervisor – Virtualization software that operates within a host operating system, enabling the simultaneous execution of several virtual machines.
* Bridged Networking – A network setup where the virtual machine shares the host's physical network adapter, acting as an independent device on the local network.
* Command Line Interface (CLI) – A text-only user interface used to interact with the OS by inputting specific text commands.
* Desktop Environment (DE) – The graphical layer of an OS offering icons, windows, toolbars, and visual utilities for easy user interaction.
* USB Passthrough – A capability allowing a virtual machine to take direct control of a physical USB device plugged into the host.

## 1. Інсталяція гіпервізора

У рамках цього завдання ми застосували гіпервізор 2-го типу — Oracle VM VirtualBox.

![Головне вікно VirtualBox](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/01_VirtualBox_Main.jpg)

## 2. Основні операції в гіпервізорі (перша віртуальна машина)

### Ініціалізація та параметри
Ми згенерували віртуальну машину з назвою **Ubuntu_Desktop_1**. Їй було призначено 25 ГБ на жорсткому диску, 2 процесорні ядра та 4 ГБ оперативної пам'яті для забезпечення безперебійного функціонування системи.

![Налаштування ВМ](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/02_VM_Settings.jpg)

### Мережеві налаштування
Вибрано конфігурацію «Мережевий міст» (Bridged Adapter). Це дозволяє віртуальній машині підключатися до локальної мережі як повноцінний самостійний вузол.

![Тип мережі](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/03_Network_Type.jpg)
![Мережевий міст](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/04_Network_Bridged.jpg)

### Робота з USB-пристроями
Ми ввімкнули підтримку контролера USB 3.0 (xHCI) і налаштували фільтр, щоб флеш-накопичувач TOSHIBA USB FLASH DRIVE монтувався до ВМ автоматично.

![USB Накопичувач](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/05_USB_Flash.jpg)

## 3. Інсталяція ОС GNU/Linux (з графічним інтерфейсом)

На створену ВМ було розгорнуто **Ubuntu Desktop 25.10** із базовою графічною оболонкою. По завершенню встановлення операційна система була повністю готова до використання через графічний інтерфейс (GUI).

![Встановлення Ubuntu](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/06_Ubuntu_Install.jpg)
![Робочий стіл Ubuntu](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/07_Ubuntu_Desktop.jpg)

## 4. Взаємодія з другою ВМ (CLI та GUI)

### Базове налаштування
Для другої машини ми обрали **Ubuntu Server**, яка за замовчуванням керується виключно через інтерфейс командного рядка (CLI).

![Server CLI](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/08_Server_CLI.jpg)

### Розгортання GNOME
За допомогою команди (`sudo apt install ubuntu-desktop`) було додано середовище GNOME, що дало змогу користуватися повноцінним графічним управлінням.

![Server GNOME](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/09_Server_GNOME.jpg)

### Інтеграція XFCE
Як альтернативу ми також інсталювали більш легку оболонку XFCE (`sudo apt install xfce4`).

![Server XFCE](https://github.com/iharecko1385/KKZ/blob/main/wrkcs2/screenshot/10_Server_XFCE.jpg)

### Аналіз GNOME та XFCE
* **GNOME** — вирізняється сучасним дизайном і багатим функціоналом (наприклад, зручним пошуком та розширеним управлінням вікнами), але при цьому потребує значно більше ресурсів комп'ютера.
* **XFCE** — є мінімалістичним і дуже легким середовищем. Воно гарантує високу швидкодію навіть за умови браку системних ресурсів, що ідеально підходить для використання у віртуальних машинах.

## Conclusion

In the course of this practical assignment, we utilized Oracle VM VirtualBox to set up two distinct virtual machines. We successfully configured the allocated hardware, enabled bridged networking, and set up USB passthrough. The first VM ran Ubuntu Desktop 25.10 as the primary graphical OS, whereas the second was initially installed as a purely CLI-based Ubuntu Server. Upon testing both GNOME and XFCE desktop environments on the server, we concluded that XFCE is much more resource-efficient and faster. Conversely, GNOME delivers a highly modern and feature-heavy interface, though it demands considerably more system resources.