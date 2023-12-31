# Detector_de_Fadiga--drowsiness_detection


O projeto de Detector de Fadiga é uma aplicação prática de Visão Computacional e Aprendizado de Máquina. 

O programa desenvolvido é capaz de identificar sinais de fadiga em tempo real, como o fechamento prolongado dos olhos, a partir de um fluxo de vídeo. 

Utilizamos para isso o detector de marcos faciais do dlib para determinar a posição dos olhos e calcular a Relação de Aspecto dos Olhos (EAR). 

Quando a EAR está abaixo de um limiar definido durante um número específico de quadros consecutivos, o programa considera que a pessoa está com sinais de fadiga e aciona um alarme.

<p align="center">
  <img 
src="https://github.com/RoseBorges44/Detector_de_Fadiga--drowsiness_detection/blob/main/Detector%20de%20fadiga.gif" alt="Demonstração em GIF">
</p>

# Estrutura do Projeto
A estrutura do projeto é a seguinte:
```bash

├── alarm.wav
├── main.py
├── requirements.txt
└── shape_predictor_68_face_landmarks.dat
```

# Descrição dos arquivos:


* `alarm.wav`: som de alarme que será tocado quando sinais de fadiga são detectados.
* `main.py`: script Python principal que contém a lógica do detector de fadiga.
* `requirements.txt`: arquivo que lista as dependências necessárias para executar o programa.
* `shape_predictor_68_face_landmarks.dat`: arquivo de dados usado pelo detector de marcos faciais do dlib.

# Pré-requisitos
Para executar este projeto, você precisa ter o Python instalado em seu sistema. As dependências do projeto são listadas no arquivo *requirements.txt* e podem ser instaladas com o seguinte comando:

```bash
pip install -r requirements.txt
```

# Execução do Projeto
Para executar o projeto, você precisa passar algumas opções para o script main.py. As opções disponíveis são:

* `-a` ou `--alarme`: define se o programa deve tocar um alarme sonoro quando detectar sinais de fadiga. Se definido como 1, o alarme será tocado. Se definido como 0, nenhum alarme será tocado. O padrão é 0.
* `-w` ou `--webcam`: define o índice da webcam a ser usado para o fluxo de vídeo. O padrão é 0.

Aqui está um exemplo de como executar o script `main.py`:

```bash
python main.py -a 1 -w 0
```

Este comando irá iniciar o detector de fadiga com um alarme sonoro e usará a webcam de índice 0 para o fluxo de vídeo.

Nota: O arquivo `shape_predictor_68_face_landmarks.dat` pode ser baixado [clicando neste link.](https://github.com/italojs/facial-landmarks-recognition/raw/master/shape_predictor_68_face_landmarks.dat)

# Detalhes do Projeto

Este programa detecta sinais de fadiga monitorando o estado dos olhos de uma pessoa em um fluxo de vídeo. O processo ocorre nas seguintes etapas:

- Captação do fluxo de vídeo em tempo real através da webcam.
- Detecção de rostos na imagem utilizando o detector de rostos do dlib.
- Detecção dos marcos faciais (em particular, os olhos) usando o preditor de marcos faciais do dlib.
- Cálculo da Relação de Aspecto dos Olhos (EAR) baseado na posição dos marcos dos olhos.
- Verificação se a EAR está abaixo do limiar definido por um determinado número de quadros consecutivos. Isso indica que a pessoa pode estar com sono.
- Se a condição acima for satisfeita, um alarme sonoro é acionado para alertar a pessoa.
- O programa utiliza o detector de marcos faciais do dlib para determinar a posição dos olhos e calcular a EAR. A EAR é uma medida que indica o grau de abertura dos olhos. - - 
- Quando a EAR está abaixo de um limiar definido durante um número específico de quadros consecutivos, o programa considera que a pessoa está com sono e aciona um alarme.

# Referências Bibliográficas
SOUKUPOVA, Tereza; CECH, Jan. [Real-time eye blink detection using facial landmarks](https://vision.fe.uni-lj.si/cvww2016/proceedings/papers/05.pdf). In: 21st computer vision winter workshop, Rimske Toplice, Slovenia. 2016.
