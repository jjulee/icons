---
---

## 설치

Bootstrap Icons는 npm 에 공개되어 있으며, 필요에 따라 수동으로 다운로드 할 수도 있습니다.

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### npm
npm으로 SVG, 아이콘 sprite, 그리고 아이콘 폰트가 포함된 [Bootstrap Icons](https://www.npmjs.com/package/bootstrap-icons)를 설치하세요. 그리고 [사용방법](#사용방법)에서 아이콘을 포함하는 방법에 대해 알아보고 선택하세요.

{{< highlight sh >}}
npm i bootstrap-icons
{{< /highlight >}}
{{< /md >}}
  </div>
  <div class="col-md-4">
{{< md >}}
### 다운로드
[모든 릴리즈는 GitHub 상에 공개](https://github.com/twbs/icons/releases/)되며 아이콘인 SVG, 폰트, 라이선스, readme가 포함되어 있습니다. `package.json` 도 포함되어 있지만, npm 스크립트는 주로 우리의 개발 워크플로우에서 이용할 수 있습니다.

<a class="btn btn-outline-primary" href="https://github.com/twbs/icons/releases/latest/">최신 ZIP 파일 다운로드</a>
{{< /md >}}
  </div>
  <div class="col-md-4">
{{< md >}}
### CDN
웹사이트의 `<head>` 또는 CSS 내에  `@import`를 사용해서 아이콘 폰트 스타일시트를 CDN으로부터 불러오도록 한 후 바로 시작하세요. [아이콘 폰트 문서](#icon-font)에서 예시를 확인해주세요.

{{< highlight html >}}
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@{{< param version >}}/font/bootstrap-icons.css">
{{< /highlight >}}

{{< highlight css >}}
@import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@{{< param version >}}/font/bootstrap-icons.css");
{{< /highlight >}}
{{< /md >}}
  </div>
</div>

## 사용방법

Bootstrap Icons는 SVG이기 때문에 프로젝트가 어떻게 설정되어 있는지에 따라 여러가지 방법으로 HTML 에 포함시킬 수 있습니다. Bootstrap Icons는 기본 `width`와 `height`가 `1em`으로 되어 있어서 `font-size`를 사용해 간단하게 크기를 변경할 수 있습니다.

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### 임베드
아이콘을 (외부 이미지 파일이 아닌) 페이지의 HTML 에 넣습니다. 여기에서는 커스텀 `width`와 `height`를 사용하고 있습니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
    {{< example >}}<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-chevron-right" viewBox="0 0 16 16"><path fill-rule="evenodd" d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708z"/></svg>{{< /example >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### Sprite
SVG sprite를 사용해 `<use>` 요소로부터 임의의 아이콘을 삽입합니다. Fragment 식별자로는 아이콘의 파일명을 사용합니다(예를 들어, `toggles`는 `#toggles`가 됩니다). SVG sprites 에서는 `<img>` 요소와 마찬가지로 외부 파일을 참조할 수 있지만, `currentColor`를 이용해 간단하게 테마를 설정할 수 있습니다.

**주의!** 현재 Chrome에서 [`<use>`가 도메인 간에서 작동하지 않는](https://bugs.chromium.org/p/chromium/issues/detail?id=470601) 문제가 있습니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
{{< example >}}
<svg class="bi" width="32" height="32" fill="currentColor">
  <use xlink:href="bootstrap-icons.svg#heart-fill"/>
</svg>
<svg class="bi" width="32" height="32" fill="currentColor">
  <use xlink:href="bootstrap-icons.svg#toggles"/>
</svg>
<svg class="bi" width="32" height="32" fill="currentColor">
  <use xlink:href="bootstrap-icons.svg#shop"/>
</svg>
{{< /example >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### 외부 이미지
Bootstrap Icons의 SVG를 임의의 디렉토리로 복사해 넣어, `<img>` 요소로 보통의 이미지와 같이 사용합니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
    {{< example >}}<img src="/assets/img/bootstrap.svg" alt="Bootstrap" width="32" height="32">{{< /example >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
### 아이콘 폰트
각 아이콘의 클래스를 가진 아이콘 폰트도 Bootstrap Icons에 포함되어 있습니다. CSS 를 통해 페이지내에 아이콘 웹 폰트를 넣어 필요에 따라 HTML 내에서 클래스를 사용합니다. (예를 들어, `<i class="bi-alarm-clock"></i>`).

아이콘의 외형을 변경하기 위해서는 `font-size` 와 `color` 를 사용합니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
    {{< example >}}<i class="bi-alarm"></i>{{< /example >}}
    {{< example >}}<i class="bi-alarm" style="font-size: 2rem; color: cornflowerblue;"></i>{{< /example >}}
  </div>
</div>

<div class="row">
  <div class="col-md-4">
{{< md >}}
### CSS
또한, CSS 내에서 SVG를 사용할 수도 있습니다 (16진수의 컬러값을 지정할 경우에는, `#` 에서 `%23`과 같이 **문자에서 벗어날 할 필요**가 있습니다). `<svg>`의 `width`와 `height`로 사이즈가 지정되어 있지 않은 경우, 아이콘은 이용 가능한 공간을 모두 채웁니다.

아이콘의 크기를 `background-size`로 변경하려면, `viewBox` 속성이 필요합니다. `xmlns` 속성은 필수입니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
{{< highlight css >}}
.bi::before {
  display: inline-block;
  content: "";
  vertical-align: -.125em;
  background-image: url("data:image/svg+xml,<svg viewBox='0 0 16 16' fill='%23333' xmlns='http://www.w3.org/2000/svg'><path fill-rule='evenodd' d='M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z' clip-rule='evenodd'/></svg>");
  background-repeat: no-repeat;
  background-size: 1rem 1rem;
}

{{< /highlight >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}

## 스타일
색상 변경은 `.text-*` 클래스나 커스텀 CSS로 가능합니다:
{{< /md >}}
  </div>
  <div class="col-md-8">
    <div class="bd-example">
      <svg class="bi bi-alert-triangle text-success" width="32" height="32" viewBox="0 0 20 20" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" d="M9.938 4.016a.146.146 0 00-.054.057L3.027 15.74a.176.176 0 00-.002.183c.016.03.037.05.054.06.015.01.034.017.066.017h13.713a.12.12 0 00.066-.017.163.163 0 00.055-.06.176.176 0 00-.003-.183L10.12 4.073a.146.146 0 00-.054-.057.13.13 0 00-.063-.016.13.13 0 00-.064.016zm1.043-.45a1.13 1.13 0 00-1.96 0L2.166 15.233c-.457.778.091 1.767.98 1.767h13.713c.889 0 1.438-.99.98-1.767L10.982 3.566z"/>
        <rect width="2" height="2" x="9.002" y="13" rx="1"/>
        <path d="M9.1 7.995a.905.905 0 111.8 0l-.35 3.507a.553.553 0 01-1.1 0L9.1 7.995z"/>
      </svg>
    </div>
{{< highlight html >}}
<svg class="bi bi-alert-triangle text-success" width="32" height="32" viewBox="0 0 20 20" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  ...
</svg>
{{< /highlight >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
## 접근성
아이콘을 장식용으로만 쓰는 게 아니라면 적절한 대체 텍스트를 제공해야 합니다. 아이콘을 추가할 때 사용한 방법과 아이콘을 사용하는 위치 (예: 독립 이미지 또는 버튼 또는 유사한 컨트롤의 유일한 컨텐츠)에 따라 다양한 방법이 있습니다. 다음은 몇 가지 예시입니다:
{{< /md >}}
  </div>
  <div class="col-md-8">
    <div class="bd-example">
      <img src="/assets/img/bootstrap.svg" alt="Bootstrap" width="32" height="32">
    </div>
{{< highlight html >}}
<!-- alt="..." on <img> element -->
<img src="/assets/img/bootstrap.svg" alt="Bootstrap" ...>
{{< /highlight >}}
    <div class="bd-example">
      <i class="bi-github" role="img" style="font-size: 2em" aria-label="GitHub"></i>
    </div>
{{< highlight html >}}
<i class="bi-github" role="img" aria-label="GitHub"></i>
{{< /highlight >}}
    <div class="bd-example">
      <svg class="bi" width="32" height="32" fill="currentColor" role="img" aria-label="Tools">
        <use xlink:href="bootstrap-icons.svg#tools"/>
      </svg>
    </div>
{{< highlight html >}}
<svg class="bi" ... role="img" aria-label="Tools">
  <use xlink:href="bootstrap-icons.svg#tools"/>
</svg>
{{< /highlight >}}
    <div class="bd-example">
      <button type="button" class="btn btn-primary" aria-label="Mute">
        <svg class="bi bi-volume-mute-fill" width="32" height="32" viewBox="0 0 16 16" fill="currentColor" xmlns="http://www.w3.org/2000/svg"><path d="M6.717 3.55A.5.5 0 017 4v8a.5.5 0 01-.812.39L3.825 10.5H1.5A.5.5 0 011 10V6a.5.5 0 01.5-.5h2.325l2.363-1.89a.5.5 0 01.529-.06zm7.137 2.096a.5.5 0 010 .708L12.207 8l1.647 1.646a.5.5 0 01-.708.708L11.5 8.707l-1.646 1.647a.5.5 0 01-.708-.708L10.793 8 9.146 6.354a.5.5 0 11.708-.708L11.5 7.293l1.646-1.647a.5.5 0 01.708 0z"></path></svg>
      </button>
    </div>
{{< highlight html >}}
<!-- aria-label="..." on the control -->
<button ... aria-label="Mute">
  <svg class="bi bi-volume-mute-fill" ...>
  ...
</svg>
{{< /highlight >}}
  </div>
</div>

<div class="row my-4">
  <div class="col-md-4">
{{< md >}}
## SVG 작업
SVG를 사용하는 것은 훌륭하지만, 몇 가지 기존의 문제들이 남아 있습니다. SVG의 사용방법이 몇 가지 있다는 점을 고려해 이 속성과 해결책을 코드에는 포함시키지 않았습니다.
{{< /md >}}
  </div>
  <div class="col-md-8">
{{< md >}}
기존의 문제는 다음과 같습니다:

- **Internet Explorer와 Edge Legacy에서는 포커스 처리가 깨져 있습니다.** SVG 를 포함시키는 경우에는, `<svg>` 요소에 `focusable="false"`를 추가해 주세요. [자세히 보기](https://stackoverflow.com/questions/18646111/disable-onfocus-event-for-svg-element)

- **브라우저는 SVG를 음성 지원이 가능한 `<img>` 태그로 일관되게 안내하지 않습니다.** 문제를 해결하기 위해서는 가능한 한 `role="img"`를 포함시켜 주세요. [자세히 보기](https://simplyaccessible.com/article/7-solutions-svgs/#acc-heading-2)

- **Internet Explorer에서는 외부 SVG sprite가 제대로 작동하지 않을 수 있습니다.** 필요에 따라 [svg4everybody](https://github.com/jonathantneal/svg4everybody) 폴리필(polyfill)을 사용해 주세요.


SVG와 관련된 다른 문제를 발견하셨나요? 세부사항이 공유될 수 있도록 [Issue]({{< param repo >}}/issues)를 만들어 주세요.
{{< /md >}}
  </div>
</div>
