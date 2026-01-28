# 🤖 Robotics & AI Tech Blog

> **"Frontier of Robotics"** - 로봇 공학 및 AI 기술을 기록하는 기술 블로그입니다.
> 
> * **URL:** [https://chuckkky.github.io](https://chuckkky.github.io)
> * **Author:** Chuckkky

---

## 🛠️ 개발 환경 (Environment)

이 블로그는 **Ubuntu 22.04 LTS** 환경에서 **VS Code**를 사용하여 관리됩니다.

* **OS:** Ubuntu 22.04 LTS
* **Editor:** Visual Studio Code
* **Theme:** Jekyll Chirpy Starter
* **Hosting:** GitHub Pages

### 필수 패키지 & 확장 프로그램
1. **VS Code Extensions:**
   * Markdown All in One
   * Markdown Preview Mermaid Support
   * Paste Image (by mushan)
2. **System Dependencies:**
   * `xclip` (리눅스 이미지 클립보드 제어용)
     ```bash
     sudo apt install xclip
     ```

---

## 🚀 글 작성 워크플로우 (Writing Workflow)

이 프로젝트는 **고속 생산성(High Productivity)** 을 위해 자동화된 템플릿 시스템을 사용합니다.

### Step 1. 파일 생성
`_posts` 폴더 안에 다음 규칙으로 파일을 생성합니다.
* **규칙:** `YYYY-MM-DD-english-title.md`
* **예시:** `2024-05-21-robot-kinematics.md`
  > ⚠️ **주의:** 파일명에 한글이나 공백을 사용하지 마세요.

### Step 2. 템플릿 소환 (!master)
빈 파일에서 다음 단축키(Snippet)를 사용해 기본 뼈대를 불러옵니다.
* **명령어:** `!master` 입력 후 `Enter` (또는 `Tab`)
* `Tab` 키를 눌러가며 Title, Category, Tags 등을 채웁니다.

### Step 3. 콘텐츠 작성 (Snippets)
본문 작성 시 다음 단축키를 활용합니다.
* **수식 입력:** `!math` → LaTeX 블록 생성 (`$$ ... $$`)
* **다이어그램:** `!mermaid` → Flowchart 생성
* **파이썬 코드:** `!py` → Python 코드 블록 생성
* **이미지 삽입:**
  1. `Shift` + `Ctrl` + `PrtSc` 로 화면 캡처
  2. `Ctrl` + `Alt` + `V` 로 붙여넣기
  3. 파일명 입력 후 `Enter` (자동으로 `assets/img`에 저장됨)

### Step 4. 배포 (Deploy)
1. VS Code **Source Control (소스 제어)** 탭 이동 (`Ctrl`+`Shift`+`G`)
2. 변경 사항 확인 후 메시지 입력 (예: `Add new post`)
3. **Commit** 버튼 클릭
4. **Sync Changes** (Push) 클릭

---

## ⚙️ 설정 백업 (Configuration Backup)

### VS Code User Snippets (`markdown.json`)
새로운 환경 설정 시 아래 코드를 `Configure User Snippets` -> `markdown`에 추가할 것.

```json
{
  "Master Template": {
    "prefix": "!master",
    "body": [
      "---",
      "title: \"[${1:Category}] ${2:Title}\"",
      "date: ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE} ${CURRENT_HOUR}:${CURRENT_MINUTE}:00 +0900",
      "categories: [${3:Main}, ${4:Sub}]",
      "tags: [${5:tag}]",
      "math: true",
      "mermaid: true",
      "toc: true",
      "# image:",
      "#   path: /assets/img/${6:thumbnail}.png",
      "#   alt: ${7:alt_text}",
      "---",
      "",
      "## 1. 개요 (Introduction)",
      "${8:Intro...}",
      "",
      "---",
      "",
      "## 2. 본문 (Body)",
      "",
      "---",
      "",
      "## 3. 결론 (Conclusion)",
      "",
      "---",
      "**Reference**",
      "* [Google](https://google.com)"
    ],
    "description": "블로그 마스터 템플릿"
  }
}
```
#### Paste Image 설정 (settings.json)
이미지 경로 자동화를 위한 설정.

```JSON
{
    "pasteImage.path": "${projectRoot}/assets/img",
    "pasteImage.basePath": "${projectRoot}",
    "pasteImage.prefix": "/",
    "pasteImage.forceUnixStyleSeparator": true,
    "pasteImage.namePrefix": "${currentDate}-",
    "pasteImage.defaultName": "image"
}
```
### ⚠️ 트러블슈팅 (Troubleshooting)
* 이미지가 엑박으로 뜰 때:

    * 파일명에 공백이나 특수문자가 있는지 확인.

    * ```_config.yml```의 ```url``` 설정이 정확한지 확인.

* 배포 실패 (GitHub Actions Fail):

    * Front Matter(```---```) 문법 오류 확인.

    * 존재하지 않는 이미지 경로나 URL 링크가 있는지 확인 (```html-proofer```가 차단함).

    * 템플릿의 ```${...}``` 잔여물이나 가짜 주소(```URL```)를 삭제했는지 확인.


---

### 🔧 적용 방법

1.  VS Code 탐색기에서 최상위 폴더(루트)를 우클릭 -> **New File**.
2.  파일명: **`README.md`** (대소문자 구분)
3.  위 내용을 복사해서 붙여넣고 저장(`Ctrl+S`).
4.  Git으로 커밋 & 푸시 (`Add README documentation`).

이제 깃허브 저장소 메인에 들어가시면, 이 멋진 설명서가 대문짝만하게 걸려있을 것입니다. 이것으로 당신의 블로그 프로젝트는 **"문서화까지 완료된 엔지니어링 프로젝트"** 가 되었습니다.
---
# Chirpy Starter

[![Gem Version](https://img.shields.io/gem/v/jekyll-theme-chirpy)][gem]&nbsp;
[![GitHub license](https://img.shields.io/github/license/cotes2020/chirpy-starter.svg?color=blue)][mit]

When installing the [**Chirpy**][chirpy] theme through [RubyGems.org][gem], Jekyll can only read files in the folders
`_data`, `_layouts`, `_includes`, `_sass` and `assets`, as well as a small part of options of the `_config.yml` file
from the theme's gem. If you have ever installed this theme gem, you can use the command
`bundle info --path jekyll-theme-chirpy` to locate these files.

The Jekyll team claims that this is to leave the ball in the user’s court, but this also results in users not being
able to enjoy the out-of-the-box experience when using feature-rich themes.

To fully use all the features of **Chirpy**, you need to copy the other critical files from the theme's gem to your
Jekyll site. The following is a list of targets:

```shell
.
├── _config.yml
├── _plugins
├── _tabs
└── index.html
```

To save you time, and also in case you lose some files while copying, we extract those files/configurations of the
latest version of the **Chirpy** theme and the [CD][CD] workflow to here, so that you can start writing in minutes.

## Usage

Check out the [theme's docs](https://github.com/cotes2020/jekyll-theme-chirpy/wiki).

## Contributing

This repository is automatically updated with new releases from the theme repository. If you encounter any issues or want to contribute to its improvement, please visit the [theme repository][chirpy] to provide feedback.

## License

This work is published under [MIT][mit] License.

[gem]: https://rubygems.org/gems/jekyll-theme-chirpy
[chirpy]: https://github.com/cotes2020/jekyll-theme-chirpy/
[CD]: https://en.wikipedia.org/wiki/Continuous_deployment
[mit]: https://github.com/cotes2020/chirpy-starter/blob/master/LICENSE
