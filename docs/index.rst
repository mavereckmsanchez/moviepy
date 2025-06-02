s/logo.png
    :width: 50%
    :align: center

**Date**: |today| **Version**: |version|

**Useful links**:
`Binary Installers <https://pypi.org/project/moviepy/>`__ |
`Source Repository <https://github.com/Zulko/moviepy>`__ |
`Issues & Ideas <https://github.com/Zulko/moviepy>`__ |
`Q&A Support <https://www.reddit.com/r/moviepy/>`__ |

MoviePy is the `Python <https://www.python.org/>`__ reference tool for video editing automation! 

It's an open source, MIT-licensed library offering user-friendly video editing 
and manipulation tools for the `Python <https://www.python.org/>`__ programming language.

.. grid:: 1 2 2 2
    :gutter: 4
    :padding: 2 2 0 0
    :class-container: sd-text-center

    .. grid-item-card:: Getting started
        :img-top: _static/medias/index_getting_started.svg
        :class-card: intro-card
     from gtts import gTTS
from moviepy.editor import TextClip, CompositeVideoClip, AudioFileClip
import os

# Seu texto explicando as técnicas proibidas de porcentagem
texto = """
Olá! Hoje vou ensinar minhas técnicas proibidas de cálculo rápido de porcentagem. 
Primeiro, para calcular 10% de um valor, basta dividir por 10. 
Depois, para 5%, basta pegar metade de 10%. 
Para 1%, divida o número por 100, e assim por diante.
Com essas técnicas, você vai resolver porcentagens rapidinho!
"""

# Passo 1: Criar o áudio com gTTS
tts = gTTS(texto, lang='pt-br')
audio_path = "audio.mp3"
tts.save(audio_path)

# Passo 2: Criar o clipe de vídeo com o texto na tela
video_duration = 20  # segundos, ajuste conforme o tempo do áudio
txt_clip = TextClip(texto, fontsize=40, color='white', bg_color='black', size=(1280, 720), method='caption')
txt_clip = txt_clip.set_duration(video_duration)

# Passo 3: Carregar o áudio e adicionar no vídeo
audio_clip = AudioFileClip(audio_path)
video = txt_clip.set_audio(audio_clip)

# Passo 4: Exportar o vídeo
video.write_videofile("tecnicas_proibidas_porcentagem.mp4", fps=24)

# Passo 5: Apagar o áudio temporário (opcional)
os.remove(audio_path)   :shadow: md

