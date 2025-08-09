# Инструкция по включению передачи файлов с PC на workspace
Чтобы включить трансфер файлов с PC на workspace необходимо проделать следующие шаги:
Зайти на Workspace, перейти в папку:
```
C:\Program Files\Amazon\WSP\
```
там будут находиться 2 файла, их необходимо скопировать в определенные папки:
- `wsp.admx` → `C:\Windows\PolicyDefinitions\`
- `wsp.adml` → `C:\Windows\PolicyDefinitions\en-US\`

![Screenshot_10](https://github.com/user-attachments/assets/cf8b7495-e2bb-4bc5-a44a-69f14c158e6a)


далее Нажми **Win+R**, введи `gpedit.msc`, нажми **Enter**.

![Screenshot_7](https://github.com/user-attachments/assets/d3d50333-3907-4d81-82fd-f984a6ebf50f)

Перейди в:
```
Computer Configuration
      → Administrative Templates
         → Amazon
            → WSP
```

![Screenshot_6](https://github.com/user-attachments/assets/55443eb9-f759-4435-94fb-ff5893e803b3)

Настрой **Configure session storage**
1. Двойной клик по **Configure session storage**.
2. Выбери **Enabled**.
3. Выбери режим передачи файлов: Download and Upload
4. Укажи папку, куда будут сохраняться файлы, например:
```
D:/session-storage
```

<img width="686" height="630" alt="Pasted image 20250809114913" src="https://github.com/user-attachments/assets/e9dbcb9f-ef34-47c7-853b-7f8e8dd47734" />


Далее создаем папку `session-storage` по пути `D:/session-storage`

Потом заходим в PowerShell **КАК АДМИНИСТРАТОР**, и выполняем:
```
gpupdate /force
```

Затем перезагружаем workspace:
В левом верхнем углу: Amzon WorkSpaces -> Restart WorkSpace

![Screenshot_9](https://github.com/user-attachments/assets/7f0b5dfa-d948-41cd-9899-268ba189a6ab)


Далее в этом же углу у нас появляется настройка File Transfer, кликаем на нее и открывается окно передачи файлов из заданной папки и в нее. Клик по файлу предлагает сохранить файл из WS на свой ПК, также можно перетянуть файл со своего ПК в окно File Transfer чтобы файл появился на WS.

![Screenshot_8](https://github.com/user-attachments/assets/87d66ab9-a33d-40c3-921a-d5c0989255bb)


