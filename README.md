# Notebooks

## Step 1. 

Clone this repository: 

```git clone https://github.com/leovaldaev/notebooks/YOLO8```

## Step 2. Create a new virtual environment

   ```python -m venv venv```

## Step 3. Activate your virtual environment

   ```source venv/bin/activate # Linux```
 
   ```.\venv\Scripts\activate # Windows```

## Step 4. Install dependencies
   
   ```python -m pip install --upgrade pip```

## Шаг 5. Установка пакетов
    
   ```pip install ultralytics```
 
   ```pip install jupyter notebook```

   ```pip install ipykernel```

## Шаг 6. Проверка установки

   Начнем с запуска jupyter notebook с команды в терминале. 
    
   ```jupyter notebook```
   
   ФОТОГРАФИЯ С СТАРТОМ

   Теперь нам нужно проверить, правильно ли мы установили YOLO v8 или нет. Для этого в открывшемся Jupyter Notebook запустим данные команды:

   ```from IPython import display```
   
   ```display.clear_output()```

   ```import ultralytics```

   ```ultralytics.checks()```
   
 ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/5.png)

   Как видите, мы успешно установили Ultralytics YOLOv8, но с процессором. Давайте теперь попробуем установить YOLOv8 с графическим процессором.
 
## Шаг 7. Конфигурация графического процессора YOLOv8
   
   Запустив данные команды мы еще раз убедимся, что YOLOv8 настроен с использованием ЦП.

   ```import torch```
   
   ```torch.cuda.is_available()```

   ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/6.PNG)

   Выходные данные имеют значение False, поскольку Torch не использует CUDA или GPU в качестве серверной части. Он использует процессор. Чтобы использовать свой графический процессор для обучения пользовательскому YOLOv8 для ваших собственных данных, вам необходимо установить torch с графическим процессором, соответствующим вашей версии CUDA.

   Итак, давайте проверим нашу версию CUDA, запустив скрипт Python в Jupyter Notebook.
   
   ```!nvidia-smi```

   ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/1.png)

   Now, we just have two stable version of Cuda(11.7 и 11.8). Поэтому нам нужно переустановаить драйверы нашей видеокарты и поставить нужную версию. В моем случае мне нужно сделать даунгрейд до версии 522.25, который будет поддерживать куду 11.8. Сопряжение версий куды и версий драйверов нвидиа, вы можете посмотреть по первой ссылке

   https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html

   ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/version_cuda_ndidia_driver.PNG)
   ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/2.png)

   ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/3.png)


   Теперь нам также нужно запустить джупутер нотебук и посмотреть установитлся ли драйвер нвидия 522.25

   ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/4.png)

   Как видим драйвер установился успешно и вместе с ним версия куда 11.8. Теперь перейдите по этой ссылке (https://pytorch.org/get-started/locally/) и выберем конфигурацию вашей системы, чтобы получить команду для установки библиотеки torch с графическим процессором.

   ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/8.PNG)

   ```pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118```

   Теперь давайте еще раз проверим правильно ли установился пакет torch c поддержкой видеокарт, командами:

    ```import torch```

    ```torch.cuda.is_available()```

    ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/9.PNG)

   Хорошо, теперь мы получаем вывод как True. Это означает, что Torch теперь использует графический процессор в качестве серверной части. Давайте теперь еще раз проверим, настроен ли YOLOv8 с графическим процессором или нет.

   ```from IPython import display```

   ```display.clear_output()```

   ```import ultralytics```

   ```ultralytics.checks()```

   ![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/10.PNG)

   Да! YOLOv8 теперь настроен с использованием графического процессора в качестве серверной части. Вы можете видеть, что он также показывает номер модели моей видеокарты NVIDIA — GeForce RTX 3060 (12 ГБ).

 ##Шаг 8. Обучение YOLOv8 на пользовательском наборе данных
   
