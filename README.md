# Actions-OpenWrt

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/P3TERX/Actions-OpenWrt/blob/main/LICENSE)

This repository contains releases of [X-WRT](https://github.com/x-wrt/x-wrt) for Mi Router 3 (mt7620) | Этот репозиторий содержит кастомные релизы [X-WRT](https://github.com/x-wrt/x-wrt) для Mi Router 3 (mt7620)

Includes support for PPPoE, WPA3, 3G/4G dongles (e.g. Huawei E3372), USB drives (NTFS, EXT4, exFAT and FAT32 file systems supported) | Включает в себя поддержку PPPoE, WPA3, 3G/4G модемов, USB флешек (NTFS, EXT4, exFAT и FAT32 файловые системы поддерживаются)

Релизы выходят каждую неделю.
Вам необходимо скачать релиз из данного репозитория (не нужно клонировать репозиторий, вам нужен только релиз)


      Установка:
      - Получаем доступ по SSH - [гайд](https://4pda.to/forum/index.php?s=&showtopic=736801&view=findpost&p=49333132)
      - Скопировать файлы openwrt-xxx-kernel1.bin и openwrt-xxx-rootfs0.bin на флешку, отформатированную в FAT32. Для удобства можно их переименовать в kernel1.bin и rootfs0.bin. Вставить флешку в роутер.
      - В консоли вводим:

      ```
      nvram set flag_last_success=1
      nvram set boot_wait=on
      nvram set uart_en=1
      nvram commit
      cd /extdisks/sda1
      mtd write kernel1.bin kernel1
      mtd write rootfs0.bin rootfs0
      reboot
      ```

      - Через несколько минут интерфейс будет доступен по адресу 192.168.15.1
      - Последующие обновления файлом openwrt-xxx-sysupgrade.bin в интерфейсе во вкладке System -> Backup / Flash Firmware -> Flash new firmware image
      - В случае неудачи - [возврат на сток через UART](https://4pda.to/forum/index.php?s=&showtopic=736801&view=findpost&p=50915904).
