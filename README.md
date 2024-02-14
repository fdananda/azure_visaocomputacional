# Azure Visão Computacional

Projeto da aula Reconhecimento Facial e transformação de imagens em Dados no Azure ML

## Configurando o serviço
1. Acessar o portal do Azure https://portal.azure.com;
2. Clicar em + Create a resource;
3. Na busca colocar "Azure AI services";
4. Clicar em "Azure AI services";
5. Clicar no botão Create ao lado de Plan - Azure AI Services;
6. Preencher o formulário. Dados utilizados:
- Subscription: Azure Subscription 1
- Resource group: laboratorio_dio 
- Region: East US
- Name: laboratoriodiovision
- Pricing Tier: Standard S0
- By checking this box I acknowledge that I have read and understood all the terms below: selecionado
>> Review + create<br>
>> Create

## Detecção de rostos no Vision Studio
1. Acessar o Vision Studio em https://portal.vision.cognitive.azure.com
2. Clique em View all resources;
3. Selecione ao lado do resource name criado no passo anterior;
>> Select as default resource<br>
>> X
4. Selecione a guia Face;
5. Selecione Detect faces in a image;
6. I acknowledge that this demo will incur usage to resource laboratoriodiovision in my Azure account: selecionado;
7. Clique no link Browse for a file no box Drag and drop a file here;
8. Selecionado o arquivo face.jpg com um rosto na foto;<br>
<img src=inputs/face.jpg width=200><br>
9. Resultado apresentado: 
- Face #1
- Face mask: no

10. Json gerado: 
```
[
  {
    "recognitionModel": "recognition_01",
    "faceRectangle": {
      "width": 452,
      "height": 411,
      "left": 387,
      "top": 214
    },
    "faceLandmarks": {
      "pupilLeft": {
        "x": 481.4,
        "y": 422.1
      },
      "pupilRight": {
        "x": 588.6,
        "y": 297.6
      },
      "noseTip": {
        "x": 557.3,
        "y": 382.4
      },
      "mouthLeft": {
        "x": 607.3,
        "y": 516.5
      },
      "mouthRight": {
        "x": 699.3,
        "y": 407.4
      },
      "eyebrowLeftOuter": {
        "x": 424.2,
        "y": 433.8
      },
      "eyebrowLeftInner": {
        "x": 468.1,
        "y": 359.9
      },
      "eyeLeftOuter": {
        "x": 467.1,
        "y": 447
      },
      "eyeLeftTop": {
        "x": 474.6,
        "y": 413.1
      },
      "eyeLeftBottom": {
        "x": 484.3,
        "y": 428.2
      },
      "eyeLeftInner": {
        "x": 499.7,
        "y": 400.1
      },
      "eyebrowRightInner": {
        "x": 523.9,
        "y": 297.3
      },
      "eyebrowRightOuter": {
        "x": 604.6,
        "y": 241.5
      },
      "eyeRightInner": {
        "x": 571,
        "y": 319.3
      },
      "eyeRightTop": {
        "x": 578.2,
        "y": 291.1
      },
      "eyeRightBottom": {
        "x": 593.5,
        "y": 301.1
      },
      "eyeRightOuter": {
        "x": 611.7,
        "y": 279
      },
      "noseRootLeft": {
        "x": 515.7,
        "y": 377.9
      },
      "noseRootRight": {
        "x": 544.6,
        "y": 337.6
      },
      "noseLeftAlarTop": {
        "x": 537.3,
        "y": 413.3
      },
      "noseRightAlarTop": {
        "x": 584.8,
        "y": 354.8
      },
      "noseLeftAlarOutTip": {
        "x": 551.5,
        "y": 446
      },
      "noseRightAlarOutTip": {
        "x": 621.8,
        "y": 365.1
      },
      "upperLipTop": {
        "x": 623.5,
        "y": 431.6
      },
      "upperLipBottom": {
        "x": 635,
        "y": 445.8
      },
      "underLipTop": {
        "x": 653.4,
        "y": 461.9
      },
      "underLipBottom": {
        "x": 669.4,
        "y": 474.9
      }
    },
    "faceAttributes": {
      "mask": {
        "type": "noMask",
        "noseAndMouthCovered": false
      }
    }
  }
]
```
11. 8. Selecionado o arquivo paisagem.jpg sem um rosto na foto;
12. Resultado apresentado: 
- No face detected

## Extração de texto de imagens no Vision Studio
13. Selecione a guia Optical character recognition;
14. Selecione "Extract text from images";
15. I acknowledge that this demo will incur usage to resource laboratoriodiovision in my Azure account: selecionado;
16. Clique no link Browse for a file no box Drag and drop a file here;
17. Selecionado o arquivo texto.jpg com um texto escrito à mão e de lado;<br>
<img src=inputs/texto.jpg width=200><br>
18. Resultado apresentado: 
"ESTUDANDOEXTRAÇÃO
DETEXTOAPARTIR
DEUNAFOTO."<br>
19. Json gerado: 
```
[
  {
    "lines": [
      {
        "text": "ESTUDANDO EXTRAÇÃO",
        "boundingPolygon": [
          {
            "x": 781,
            "y": 209
          },
          {
            "x": 775,
            "y": 1447
          },
          {
            "x": 656,
            "y": 1446
          },
          {
            "x": 657,
            "y": 209
          }
        ],
        "words": [
          {
            "text": "ESTUDANDO",
            "boundingPolygon": [
              {
                "x": 780,
                "y": 231
              },
              {
                "x": 764,
                "y": 871
              },
              {
                "x": 656,
                "y": 869
              },
              {
                "x": 656,
                "y": 227
              }
            ],
            "confidence": 0.988
          },
          {
            "text": "EXTRAÇÃO",
            "boundingPolygon": [
              {
                "x": 764,
                "y": 956
              },
              {
                "x": 767,
                "y": 1440
              },
              {
                "x": 658,
                "y": 1440
              },
              {
                "x": 656,
                "y": 954
              }
            ],
            "confidence": 0.952
          }
        ]
      },
      {
        "text": "DE TEXTO A PARTIR",
        "boundingPolygon": [
          {
            "x": 605,
            "y": 210
          },
          {
            "x": 630,
            "y": 1334
          },
          {
            "x": 516,
            "y": 1338
          },
          {
            "x": 492,
            "y": 210
          }
        ],
        "words": [
          {
            "text": "DE",
            "boundingPolygon": [
              {
                "x": 606,
                "y": 234
              },
              {
                "x": 606,
                "y": 354
              },
              {
                "x": 492,
                "y": 350
              },
              {
                "x": 492,
                "y": 229
              }
            ],
            "confidence": 0.995
          },
          {
            "text": "TEXTO",
            "boundingPolygon": [
              {
                "x": 607,
                "y": 423
              },
              {
                "x": 611,
                "y": 705
              },
              {
                "x": 497,
                "y": 703
              },
              {
                "x": 492,
                "y": 420
              }
            ],
            "confidence": 0.991
          },
          {
            "text": "A",
            "boundingPolygon": [
              {
                "x": 613,
                "y": 803
              },
              {
                "x": 615,
                "y": 865
              },
              {
                "x": 502,
                "y": 865
              },
              {
                "x": 500,
                "y": 803
              }
            ],
            "confidence": 0.992
          },
          {
            "text": "PARTIR",
            "boundingPolygon": [
              {
                "x": 618,
                "y": 964
              },
              {
                "x": 629,
                "y": 1318
              },
              {
                "x": 527,
                "y": 1322
              },
              {
                "x": 507,
                "y": 965
              }
            ],
            "confidence": 0.98
          }
        ]
      },
      {
        "text": "DE UNA FOTO.",
        "boundingPolygon": [
          {
            "x": 423,
            "y": 207
          },
          {
            "x": 491,
            "y": 1063
          },
          {
            "x": 370,
            "y": 1067
          },
          {
            "x": 312,
            "y": 208
          }
        ],
        "words": [
          {
            "text": "DE",
            "boundingPolygon": [
              {
                "x": 425,
                "y": 227
              },
              {
                "x": 430,
                "y": 349
              },
              {
                "x": 316,
                "y": 349
              },
              {
                "x": 312,
                "y": 226
              }
            ],
            "confidence": 0.994
          },
          {
            "text": "UNA",
            "boundingPolygon": [
              {
                "x": 435,
                "y": 434
              },
              {
                "x": 450,
                "y": 660
              },
              {
                "x": 335,
                "y": 662
              },
              {
                "x": 320,
                "y": 434
              }
            ],
            "confidence": 0.952
          },
          {
            "text": "FOTO.",
            "boundingPolygon": [
              {
                "x": 460,
                "y": 775
              },
              {
                "x": 490,
                "y": 1052
              },
              {
                "x": 379,
                "y": 1055
              },
              {
                "x": 346,
                "y": 777
              }
            ],
            "confidence": 0.977
          }
        ]
      }
    ]
  }
]
```
Obs.: a inteligência artificial interpretou a letra m como um n.

## Criação de legendas no Vision Studio
20. Selecione a guia Image Analysis;
21. Selecione a opção Add captions to images;
22. Selecionado o arquivo face.jpg com um rosto na foto;<br>
<img src=inputs/face.jpg width=200><br>
23. Resultado apresentado: 
A woman taking a selfie under a tree
24. Json gerado: 
```
{
  "apim-request-id": "378fdfa3-dded-4628-bf4c-8e2b804719c5",
  "content-length": "165",
  "content-type": "application/json; charset=utf-8",
  "modelVersion": "2023-10-01",
  "captionResult": {
    "text": "a woman taking a selfie under a tree",
    "confidence": 0.7918692827224731
  },
  "metadata": {
    "width": 1426,
    "height": 1426
  }
}
```
25. Selecionado o arquivo paisagem.jpg;<br>
<img src=inputs/paisagem.JPG width=200><br>
23. Resultado apresentado: 
A forest of trees and mountains
24. Json gerado: 
```
{
  "apim-request-id": "bb897392-f32f-4524-8a0d-24ba04985a31",
  "content-length": "158",
  "content-type": "application/json; charset=utf-8",
  "modelVersion": "2023-10-01",
  "captionResult": {
    "text": "a forest of trees and mountains",
    "confidence": 0.70673668384552
  },
  "metadata": {
    "width": 4860,
    "height": 3888
  }
}
```

Ref.: documento criado como projeto em treinamento da Dio e com base na documentação oficial, disponível no endereço: https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/04-face.html / https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/05-ocr.html e https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/03-image-analysis.html

