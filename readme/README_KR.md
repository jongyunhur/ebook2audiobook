# 📚 ebook2audiobook
CPU/GPU를 사용하여 eBook을 챕터 및 메타데이터와 함께 오디오북으로 변환하는 도구입니다.<br/>
Calibre, ffmpeg, XTTSv2, Fairseq 등을 활용하며, 음성 클로닝 및 1110개 이상의 언어를 지원합니다!
> [!IMPORTANT]
**이 도구는 DRM이 없는 합법적으로 획득한 eBook에만 사용해야 합니다.** <br>
저자는 이 소프트웨어의 오용이나 법적 결과에 대해 책임을 지지 않습니다. <br>
이 도구를 책임감 있게 사용하고 관련 법률을 준수하세요.

[![Discord](https://dcbadge.limes.pink/api/server/https://discord.gg/63Tv3F65k6)](https://discord.gg/63Tv3F65k6)

ebook2audiobook 개발을 지원해 주세요!<br>
[![Ko-Fi](https://img.shields.io/badge/Ko--fi-F16061?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/athomasson2) 


#### GUI 인터페이스
![demo_web_gui](assets/demo_web_gui.gif)

<details>
  <summary>웹 GUI 이미지를 보려면 클릭하세요</summary>
  <img width="1728" alt="GUI Screen 1" src="assets/gui_1.png">
  <img width="1728" alt="GUI Screen 2" src="assets/gui_2.png">
  <img width="1728" alt="GUI Screen 3" src="assets/gui_3.png">
</details>


## README.md 번역
- ara [العربية (Arabic)](./readme/README_AR.md)
- zho [中文 (Chinese)](./readme/README_CN.md)
- eng [English](README.md)
- swe [Svenska (Swedish)](./readme/README_SWE.md)
- fas [فارسی (Persian)](./readme/README_FA.md)
- kor [한국어 (Korean)](./readme/README_KR.md)
- ita [Italiano (Italian)](./readme/README.it.md)



## 목차
- [ebook2audiobook](#-ebook2audiobook)
- [기능](#기능)
- [Docker GUI 인터페이스](#Docker-GUI-인터페이스)
- [Huggingface Space 데모](#Huggingface-Space-데모)
- [무료 Google Colab](#무료-Google-Colab)
- [미리 제작된 오디오 데모](#데모)
- [지원 언어](#지원-언어)
- [시스템 요구 사항](#시스템-요구-사항)
- [설치 방법](#설치-방법)
- [사용법](#Gradio-웹-인터페이스-실행)
  - [Gradio 웹 인터페이스 실행](#Gradio-웹-인터페이스-실행)
  - [기본 Headless 사용법](#기본-사용법)
  - [Headless Custom XTTS Model Usage](#사용자-지정-모델-ZIP-업로드-예시)
  - [GPU 대여](#GPU-대여)
  - [도움말 명령 출력](#help-command-output)
- [Fine-Tuned TTS 모델](#Fine-Tuned-TTS-모델)
  - [Fine-Tuned TTS 모델 모음](#Fine-Tuned-TTS-모델-컬렉션)
- [Docker 사용하기](#Docker-사용하기)
  - [Docker 실행](#Docker-컨테이너-실행)
  - [Docker 빌드](#Docker-컨테이너-빌드)
  - [Docker Compose](#docker-compose)
  - [Headless Docker 가이드](#Headless-Docker-가이드)
  - [Docker 컨테이너 파일 위치](#Docker-컨테이너-파일-위치)
  - [일반적인 Docker Issues 해결](#일반적인-Docker-Issues-해결)
- [지원되는 eBook 형식](#지원되는-eBook-형식)
- [출력](#출력)
- [일반적인 Issue 및 해결 방법](#일반적인-Issue-및-해결-방법)
- [특별 감사](#special-thanks)
- [서버 참여](#우리와-함께하세요!)
- [이전 버전](#legacy-v10)
- [목차](#목차)


## 기능
- 📖 Calibre를 사용하여 eBook을 텍스트 형식으로 변환
- 📚 챕터별로 eBook을 분할하여 체계적인 오디오 생성
- 🎙️ [Coqui XTTSv2](https://huggingface.co/coqui/XTTS-v2) 및 [Fairseq](https://github.com/facebookresearch/fairseq/tree/main/examples/mms) 등 고품질 음성생성 엔진 지원
- 🗣️ 사용자의 음성을 활용한 음성 복제 기능 제공
- 🌍 1110개 이상의 언어 지원 (기본값: 영어) [지원 언어 목록](https://dl.fbaipublicfiles.com/mms/tts/all-tts-languages.html)
- 🖥️ 4GB RAM에서도 실행 가능


## [Huggingface space 데모](https://huggingface.co/spaces/drewThomasson/ebook2audiobook)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Spaces-yellow?style=for-the-badge&logo=huggingface)](https://huggingface.co/spaces/drewThomasson/ebook2audiobook)
- 무료 CPU Tier에서 실행되므로 속도가 느리거나 시간 초과가 발생할 수 있으니, 너무 큰 파일은 피해주세요
- 공간을 복제하거나 로컬에서 실행하는 것이 가장 좋습니다.


## 무료 Google Colab 
[![Free Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DrewThomasson/ebook2audiobook/blob/main/Notebooks/colab_ebook2audiobook.ipynb)


## 지원 언어
| **Arabic (ar)**    | **Chinese (zh)**    | **English (en)**   | **Spanish (es)**   |
|:------------------:|:------------------:|:------------------:|:------------------:|
| **French (fr)**    | **German (de)**     | **Italian (it)**   | **Portuguese (pt)** |
| **Polish (pl)**    | **Turkish (tr)**    | **Russian (ru)**   | **Dutch (nl)**     |
| **Czech (cs)**     | **Japanese (ja)**   | **Hindi (hi)**     | **Bengali (bn)**   |
| **Hungarian (hu)** | **Korean (ko)**     | **Vietnamese (vi)**| **Swedish (sv)**   |
| **Persian (fa)**   | **Yoruba (yo)**     | **Swahili (sw)**   | **Indonesian (id)**|
| **Slovak (sk)**    | **Croatian (hr)**   | **Tamil (ta)**     | **Danish (da)**    |
- [**+1100개 이상의 언어 및 방언 목록**](https://dl.fbaipublicfiles.com/mms/tts/all-tts-languages.html)


##  시스템 요구 사항
- 최소 4GB RAM (권장: 8GB)
- Windows에서 실행할 경우 가상화 활성화 필요 (Docker 전용)
- CPU, GPU(권장), MPS(아직 최적화되지 않아 CPU보다 느릴 수 있음)와 호환됩니다.

> [!IMPORTANT]
**설치 또는 버그 관련 문제를 게시하기 전에,<br>
열린 이슈와 닫힌 이슈 탭을 신중하게 검색하여 이미 존재하는 문제인지 확인하세요.**


>[!NOTE]
**장(chapter), 단락(paragraph), 서문(preface) 등의 표준 구조가 없기 때문에,<br>
오디오로 변환하고 싶지 않은 텍스트는 먼저 수동으로 제거해야 합니다.**


### 설치 방법
1. **저장소 클론**
```bash
git clone https://github.com/DrewThomasson/ebook2audiobook.git
```

### Gradio 웹 인터페이스 실행
1. **ebook2audiobook 실행하기**:
   - **Linux/MacOS**
     ```bash
     ./ebook2audiobook.sh  # Run Launch script
     ```
   - **Windows**
     ```bash
     .\ebook2audiobook.cmd  # Run launch script or double click on it (Bypass windows alerts)
     ```
2. **웹 앱 열기**: 터미널에 제공된 URL을 클릭하여 웹 앱에 접속하고 eBook을 변환하세요
3. **공개 링크 생성**:
   `python app.py --share` (all OS)
   `./ebook2audiobook.sh --share` (Linux/MacOS)
   `ebook2audiobook.cmd --share` (Windows)

> [!IMPORTANT]
**스크립트를 중지했다가 다시 실행하면, 웹 페이지가 새로운 연결 소켓에 접속할 수 있도록
Gradio GUI 인터페이스를 새로고침해야 합니다.**

### 기본 사용법
   - **Linux/MacOS**:
     ```bash
     ./ebook2audiobook.sh --headless --ebook <path_to_ebook_file> \
         --voice [path_to_voice_file] --language [language_code]
     ```
   - **Windows**
     ```bash
     .\ebook2audiobook.cmd --headless --ebook <path_to_ebook_file>
         --voice [path_to_voice_file] --language [language_code]
     ```
     
  - **[--ebook]**: eBook 파일 경로
  - **[--voice]**: 음성 클로닝 파일 경로 (선택 사항)
  - **[--language]**: ISO-639-3 언어 코드 (예: 이탈리아어 - ita, 영어 - eng, 독일어 - deu 등)<br>
    기본 언어는 eng이며, --language 옵션을 생략하면 ./lib/lang.py에 설정된 기본 언어가 사용됩니다.<br>
    또한, ISO-639-1 두 글자 코드도 지원됩니다.


###  사용자 지정 모델 ZIP 업로드 예시
  (필수 모델 파일이 포함된 .zip 파일이어야 합니다. XTTS의 예: config.json, model.pth, vocab.json, ref.wav)
   - **Linux/MacOS**
     ```bash
     ./ebook2audiobook.sh --headless --ebook <ebook_file_path> \
         --voice <target_voice_file_path> --language <language> --custom_model <custom_model_path>
     ```
   - **Windows**
     ```bash
     .\ebook2audiobook.cmd --headless --ebook <ebook_file_path> \
         --voice <target_voice_file_path> --language <language> --custom_model <custom_model_path>
     ```
- **<custom_model_path>**: `model_name.zip` 파일의 경로로,
      TTS 엔진에 따라 필수 파일이 모두 포함되어 있어야 합니다.<br>
      (자세한 내용은 ./lib/models.py 참고)


### 모든 매개변수 목록과 자세한 가이드를 보려면
   - **Linux/MacOS**
     ```bash
     ./ebook2audiobook.sh --help
     ```
   - **Windows**
     ```bash
     .\ebook2audiobook.cmd --help
     ```
   - **Or for all OS**
    ```python
     app.py --help
    ```

<a id="help-command-output"></a>
```bash
usage: app.py [-h] [--script_mode SCRIPT_MODE] [--session SESSION] [--share]
              [--headless] [--ebook EBOOK] [--ebooks_dir EBOOKS_DIR]
              [--language LANGUAGE] [--voice VOICE] [--device {cpu,gpu,mps}]
              [--tts_engine {xtts,bark,vits,fairseq,yourtts}]
              [--custom_model CUSTOM_MODEL] [--fine_tuned FINE_TUNED]
              [--output_format OUTPUT_FORMAT] [--temperature TEMPERATURE]
              [--length_penalty LENGTH_PENALTY] [--num_beams NUM_BEAMS]
              [--repetition_penalty REPETITION_PENALTY] [--top_k TOP_K] [--top_p TOP_P]
              [--speed SPEED] [--enable_text_splitting] [--output_dir OUTPUT_DIR]
              [--version]

Convert eBooks to Audiobooks using a Text-to-Speech model. You can either launch the Gradio interface or run the script in headless mode for direct conversion.

options:
  -h, --help            show this help message and exit
  --session SESSION     Session to resume the conversion in case of interruption, crash, 
                            or reuse of custom models and custom cloning voices.

**** The following option are for gradio/gui mode only:
  Optional

  --share               Enable a public shareable Gradio link.

**** The following options are for --headless mode only:
  --headless            Run the script in headless mode
  --ebook EBOOK         Path to the ebook file for conversion. Cannot be used when --ebooks_dir is present.
  --ebooks_dir EBOOKS_DIR
                        Relative or absolute path of the directory containing the files to convert. 
                            Cannot be used when --ebook is present.
  --language LANGUAGE   Language of the e-book. Default language is set 
                            in ./lib/lang.py sed as default if not present. All compatible language codes are in ./lib/lang.py

optional parameters:
  --voice VOICE         (Optional) Path to the voice cloning file for TTS engine. 
                            Uses the default voice if not present.
  --device {cpu,gpu,mps}
                        (Optional) Pprocessor unit type for the conversion. 
                            Default is set in ./lib/conf.py if not present. Fall back to CPU if GPU not available.
  --tts_engine {xtts,bark,vits,fairseq,yourtts}
                        (Optional) Preferred TTS engine (available are: ['xtts', 'bark', 'vits', 'fairseq', 'yourtts'].
                            Default depends on the selected language. The tts engine should be compatible with the chosen language
  --custom_model CUSTOM_MODEL
                        (Optional) Path to the custom model zip file cntaining mandatory model files. 
                            Please refer to ./lib/models.py
  --fine_tuned FINE_TUNED
                        (Optional) Fine tuned model path. Default is builtin model.
  --output_format OUTPUT_FORMAT
                        (Optional) Output audio format. Default is set in ./lib/conf.py
  --temperature TEMPERATURE
                        (xtts only, optional) Temperature for the model. 
                            Default to config.json model. Higher temperatures lead to more creative outputs.
  --length_penalty LENGTH_PENALTY
                        (xtts only, optional) A length penalty applied to the autoregressive decoder. 
                            Default to config.json model. Not applied to custom models.
  --num_beams NUM_BEAMS
                        (xtts only, optional) Controls how many alternative sequences the model explores. Must be equal or greater than length penalty. 
                            Default to config.json model.
  --repetition_penalty REPETITION_PENALTY
                        (xtts only, optional) A penalty that prevents the autoregressive decoder from repeating itself. 
                            Default to config.json model.
  --top_k TOP_K         (xtts only, optional) Top-k sampling. 
                            Lower values mean more likely outputs and increased audio generation speed. 
                            Default to config.json model.
  --top_p TOP_P         (xtts only, optional) Top-p sampling. 
                            Lower values mean more likely outputs and increased audio generation speed. Default to 0.85
  --speed SPEED         (xtts only, optional) Speed factor for the speech generation. 
                            Default to config.json model.
  --enable_text_splitting
                        (xtts only, optional) Enable TTS text splitting. This option is known to not be very efficient. 
                            Default to config.json model.
  --output_dir OUTPUT_DIR
                        (Optional) Path to the output directory. Default is set in ./lib/conf.py
  --version             Show the version of the script and exit

Example usage:    
Windows:
    Gradio/GUI:
    ebook2audiobook.cmd
    Headless mode:
    ebook2audiobook.cmd --headless --ebook '/path/to/file'
Linux/Mac:
    Gradio/GUI:
    ./ebook2audiobook.sh
    Headless mode:
    ./ebook2audiobook.sh --headless --ebook '/path/to/file'
```

참고: Gradio/GUI 모드에서 실행 중인 변환을 취소하려면 eBook 업로드 구성 요소에서 [X] 버튼을 클릭하세요.

### Docker 사용하기
Docker를 사용하여 eBook을 오디오북으로 변환할 수도 있습니다.
이 방법은 다양한 환경에서 일관성을 유지하고 설정을 간소화하는 데 도움이 됩니다.


#### Docker 컨테이너 실행
Docker 컨테이너를 실행하고 Gradio 인터페이스를 시작하려면 다음 명령어를 사용하세요.

 -Run with CPU only
```powershell
docker run --rm -p 7860:7860 athomasson2/ebook2audiobook
```
 -Run with GPU Speedup (NVIDIA compatible only)
```powershell
docker run --rm --gpus all -p 7860:7860 athomasson2/ebook2audiobook
```


#### Docker 컨테이너 빌드
- 다음 명령어로 Docker 이미지를 빌드할 수 있습니다:
```powershell
docker build --platform linux/amd64 -t athomasson2/ebook2audiobook .
```
이 명령어를 실행하면 Gradio 인터페이스가 포트 7860(`localhost:7860`)에서 시작됩니다.
- 추가 옵션을 확인하려면 `--help` 매개변수를 사용하세요.


## Docker 컨테이너 파일 위치
모든 eBook2Audiobook 파일의 기본 디렉터리는 `/home/user/app/`입니다.
For example:
`tmp` = `/home/user/app/tmp`
`audiobooks` = `/home/user/app/audiobooks`


## Headless Docker 가이드
먼저, 최신 버전의 Docker 이미지를 가져오려면 다음 명령어를 실행하세요:
```bash 
docker pull athomasson2/ebook2audiobook
```
- 실행하기 전에, 현재 디렉터리에 "input-folder"라는 폴더를 생성해야 합니다.
이 폴더는 Docker 컨테이너와 연결되며, 변환할 입력 파일을 저장하는 위치입니다.
```bash
mkdir input-folder && mkdir Audiobooks
```
아래 명령어에서 **YOUR_INPUT_FILE.TXT** 을 변환할 eBook 파일 이름으로 변경하세요.
```bash
docker run --rm \
    -v $(pwd)/input-folder:/home/user/app/input_folder \
    -v $(pwd)/audiobooks:/home/user/app/audiobooks \
    athomasson2/ebook2audiobook \
    --headless --ebook /input_folder/YOUR_EBOOK_FILE
```
- 이제 변환된 오디오북은 Audiobooks 폴더에 저장되며, 해당 폴더는 Docker 명령어를 실행한 로컬 디렉터리에 위치합니다.


## 기타 매개변수 확인 방법
이 프로그램에서 사용할 수 있는 다른 매개변수를 확인하려면 다음 명령어를 실행하세요:
```bash
docker run --rm athomasson2/ebook2audiobook --help

```
이 명령어를 실행하면 다음과 같은 출력이 표시됩니다:
[도움말 명령 출력](#help-command-output)


### Docker Compose
이 프로젝트는 Docker Compose를 사용하여 로컬에서 실행됩니다.
`docker-compose.yml`에서 `*gpu-enabled` 또는 `*gpu-disabled`를 설정하여 GPU 지원을 활성화하거나 비활성화할 수 있습니다.


#### 실행 방법
1. **Clone the Repository** (아직 하지 않았다면):
   ```bash
   git clone https://github.com/DrewThomasson/ebook2audiobook.git
   cd ebook2audiobook
   ```
2. **GPU 지원 설정 (기본적으로 비활성화됨)**
  `docker-compose.yml`을 수정하여 `*gpu-disabled`를 `*gpu-enabled`로 변경하면 GPU 지원을 활성화할 수 있습니다.
3. **서비스 접속:**
    ```bash
    docker-compose up -d
    ```
4. **서비스 접속:**
  웹 인터페이스는 http://localhost:7860 에서 사용할 수 있습니다.


### Docker GUI 인터페이스
![demo_web_gui](assets/demo_web_gui.gif)

<details>
  <summary>웹 GUI 이미지 보기를 클릭하세요.</summary>
  <img width="1728" alt="GUI Screen 1" src="assets/gui_1.png">
  <img width="1728" alt="GUI Screen 2" src="assets/gui_2.png">
  <img width="1728" alt="GUI Screen 3" src="assets/gui_3.png">
</details>


## GPU 대여
직접 실행할 하드웨어가 없거나 GPU를 대여하고 싶다면?
#### Hugging Face Space에서 GPU 대여 (시간당 약 $0.40)
[Huggingface Space 데모](#Huggingface-Space-데모)

#### 또는 무료 Google Colab 사용!
(Google Colab은 일정 시간 동안 활동이 없으면 자동으로 세션이 종료될 수 있습니다.)
[무료 Google Colab](#무료-Google-Colab)


## 일반적인 Docker Issues 해결

- `python: can't open file '/home/user/app/app.py': [Errno 2] No such file or directory` 
<br>해결 방법: 추가 인수를 제거하세요. Dockerfile에서 `CMD`를 `ENTRYPOINT`로 변경했기 때문입니다.
  - 예시 (잘못된 명령어):
  ```bash
  docker run athomasson2/ebook2audiobook app.py --script_mode full_docker
  ```
  수정된 명령어:
  ```bash
  `docker run athomasson2/ebook2audiobook`
  ```
  - 추가 인수는 다음과 같이 간단하게 추가할 수 있습니다:
  ```bash
  docker run athomasson2/ebook2audiobook --share
  ```

- Docker가 Fine-Tuned 모델 다운로드 중 멈춤
  <br>일부 시스템에서 발생하는 문제이며, 진행률 표시줄을 비활성화하면 해결될 수 있습니다.
  [GitHub Issue #191](https://github.com/DrewThomasson/ebook2audiobook/issues/191)에서 논의된 해결 방법을 참고하세요.
  <br>해결 방법:
  다음과 같이 환경 변수를 설정하여 진행률 표시줄을 비활성화하세요.
```Dockerfile
docker run --rm --gpus all -e HF_HUB_DISABLE_PROGRESS_BARS=1 -e HF_HUB_ENABLE_HF_TRANSFER=0 \
    -p 7860:7860 athomasson2/ebook2audiobook
```


## Fine-Tuned TTS 모델
자신만의 XTTS 모델을 쉽게 파인튜닝하려면 다음 repository를 사용하세요.
[xtts-finetune-webui](https://github.com/daswer123/xtts-finetune-webui)

GPU를 간편하게 대여하여 파인튜닝을 실행하려면 다음 Hugging Face Space를 복제하세요.
[xtts-finetune-webui-space](https://huggingface.co/spaces/drewThomasson/xtts-finetune-webui-gpu)

훈련 데이터를 쉽게 잡음 제거하려면 다음 Hugging Face Space를 사용하세요.
[denoise-huggingface-space](https://huggingface.co/spaces/drewThomasson/DeepFilterNet2_no_limit)

### Fine-Tuned TTS 모델 컬렉션
이미 파인튜닝된 TTS 모델 컬렉션을 확인하려면 아래 링크를 방문하세요.
[this Hugging Face link](https://huggingface.co/drewThomasson/fineTunedTTSModels/tree/main)
XTTS 사용자 지정 모델을 사용하려면 반드시 음성 참조용 오디오 클립이 필요합니다.


## 데모
**Rainy day voice**
https://github.com/user-attachments/assets/d25034d9-c77f-43a9-8f14-0d167172b080


**David Attenborough voice**
https://github.com/user-attachments/assets/0d437a41-0b0d-48ed-8c9b-02763d5e48ea


## 지원되는 eBook 형식
- `.epub`, `.pdf`, `.mobi`, `.txt`, `.html`, `.rtf`, `.chm`, `.lit`,
  `.pdb`, `.fb2`, `.odt`, `.cbr`, `.cbz`, `.prc`, `.lrf`, `.pml`,
  `.snb`, `.cbc`, `.rb`, `.tcr`
- **최적의 결과**를 위해 자동 챕터 감지가 가능한 `.epub` 또는 `.mobi` 형식을 권장합니다.


## 출력
- `['m4b', 'm4a', 'mp4', 'webm', 'mov', 'mp3', 'flac', 'wav', 'ogg', 'aac']` 형식의 오디오 파일을 생성하며, 메타데이터와 챕터 정보가 포함됩니다.
<br> (설정 파일: `./lib/conf.py`)
- **예제 출력**
  ![예제](https://github.com/DrewThomasson/VoxNovel/blob/dc5197dff97252fa44c391dc0596902d71278a88/readme_files/example_in_app.jpeg)


## 일반적인 Issue 및 해결 방법:
-  CPU 속도가 느림
  - 서버용 SMP CPU에서는 더 나은 성능을 보이며, NVIDIA GPU를 사용하면 거의 실시간 변환이 가능합니다.
  - 관련 논의: [여기에서 확인](https://github.com/DrewThomasson/ebook2audiobook/discussions/19#discussioncomment-10879846)
  - 다국어 오디오를 더 빠르게 생성하려면 [piper-tts 기반 프로젝트](https://github.com/DrewThomasson/ebook2audiobookpiper-tts) 를 고려하세요.
  (단, 제로샷 음성 복제는 지원하지 않으며, Siri 수준의 음질이지만 CPU에서 훨씬 빠르게 실행됩니다.)
- "의존성 문제로 실행이 안 돼요!" 
  - Docker를 사용하세요. Docker는 완전한 독립 실행 환경을 제공하며, 헤드리스 모드도 지원합니다.
  - 더 많은 옵션을 보려면 Docker 실행 명령에 --help 파라미터를 추가하세요.
- "출력된 오디오가 잘려요!" 
  - 이 문제를 겪으셨다면 반드시 GitHub에 Issue를 올려 주세요!
  - 모든 언어를 직접 테스트할 수 없기 때문에, 사용자 피드백을 통해 문장 분할 로직을 최적화할 필요가 있습니다. 😊


## 도움이 필요해요! 🙌 
## [전체 목록은 여기에서 확인하세요](https://github.com/DrewThomasson/ebook2audiobook/issues/32)
- 지원되는 언어를 구사하는 분들의 도움을 받아, 올바른 문장 분할 방식을 개선하고 싶습니다.
- 다양한 언어로 README 가이드를 작성해 주실 분이 필요합니다! (제가 아는 언어는 영어뿐이에요 😔)


## Special Thanks
- **Coqui TTS**: [Coqui TTS GitHub](https://github.com/idiap/coqui-ai-TTS)
- **Calibre**: [Calibre 공식 웹사이트](https://calibre-ebook.com)
- **FFmpeg**: [FFmpeg 공식 웹사이트](https://ffmpeg.org)
- [@shakenbake15 - 더 나은 챕터 저장 방식 제안](https://github.com/DrewThomasson/ebook2audiobook/issues/8) 


### [Legacy V1.0](legacy/v1.0)
이전 버전의 코드는 [여기에서 확인](legacy/v1.0) 할 수 있습니다.


## 우리와 함께하세요!
[![Discord](https://dcbadge.limes.pink/api/server/https://discord.gg/63Tv3F65k6)](https://discord.gg/63Tv3F65k6)