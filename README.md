# Notebooks
- Step 1. Clone this repository: https://github.com/leovaldaev/notebooks/YOLO8

- Step 2. Create a new virtual environment

   ```python -m venv venv```

 - Step 3. Activate your virtual environment

   ```source venv/bin/activate # Linux```
 
   ```.\venv\Scripts\activate # Windows```

 - Step 4. Install dependencies
   
   ```python -m pip install --upgrade pip```
 
   ```pip install -r requirements.txt```

 - Step 5. Install packages
    
   ```pip install ultralytics```
 
   ```pip install jupyter notebook```

 - Step 6. Start jupyter notebook
    
   ```jupyter notebook```
 
   ```!nvidia-smi```

![Image alt](https://github.com/leovaldaev/Images_for_project/blob/main/YOLOv8/1.png)

 - Step 7. Now, we just have two stable version of Cuda(11.7 и 11.8), которые бы поддерживал бы пайторч. Поэтому нам нужно переустановаить
   драйверы нашей видеокарты и поставить нужную версию. В моем случае мне нужно сделать даунгрейд до версии 522.25, который будет поддерживать         куду 11.8. Сопряжение версий куды и версий драйверов нвидиа, вы можете посмотреть по первой ссылке

   ![Image alt](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html)
 
   ```.\venv\Scripts\activate # Windows```
