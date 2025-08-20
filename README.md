# transfer_learning_dio
# Instalação

- Python 3.12.11
- Suba a pasta requirements para o diretório:
-"/content/sample_data" dentro do colab
- Instalar dependências:
- !pip install -r requirements.txt
 
- Baixe o dataset no seguinte endereço:
-"https://www.microsoft.com/en-us/download/details.aspx?id=54765"
- Suba o arquivo "kagglecatsanddogs_5340.zip" para o seguinte caminho:
- "/content/sample_data/kagglecatsanddogs_5340.zip"

- Execute célula por célula


- Na útima célula:
 # Caminho da imagem que você quer testar
- img_path = "Caminho_da_sua_imagem" localize essa variável no código e escolha o caminho da sua imagem

  
import numpy as np
import matplotlib.pyplot as plt
from tensorflow.keras.preprocessing import image
from PIL import Image

# Função para carregar e pré-processar a imagem para o modelo
def get_image(path, target_size=(96, 96)):
    """
    Carrega uma imagem redimensionada para o modelo e retorna:
    - img: objeto PIL redimensionado (para referência, não para plot)
    - x: array numpy pré-processado, shape=(1, H, W, 3)
    """
    img = image.load_img(path, target_size=target_size)
    x = image.img_to_array(img)
    x = np.expand_dims(x, axis=0)
    x = x / 255.0  # normalização para o modelo
    return img, x

# Lista de categorias
categories = ['Cat', 'Dog']

# Caminho da imagem que você quer testar
img_path = '/content/sample_data/cachorro-da-raca-lulu-da-pomeramia-1648065976007_v2_1x1.jpg' ### Coloque o caminho da sua imagem para utilizar o modelo na prática

# Carrega a imagem redimensionada para o modelo
img_model, x = get_image(img_path, target_size=(96,96))

# Faz a previsão
probabilities = model_new.predict(x)  # sem colchetes

# Classe prevista
pred_class = np.argmax(probabilities)
print(f"Classe prevista: {categories[pred_class]}, Probabilidade: {probabilities[0][pred_class]:.2f}")

# Carrega a imagem ORIGINAL para exibição
img_original = Image.open(img_path)  # mantém resolução original

# Mostra a imagem original
plt.figure(figsize=(6,6))
plt.imshow(img_original)
plt.axis('off')
plt.show()
