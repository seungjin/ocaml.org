<!-- ((! set title Install OCaml !)) ((! set documentation !)) -->

*Table of contents*

# OCaml 설치하기
OCaml 컴파일러와 라이브러리들은 여러가지 다양한 방법을 통하여 설치 될수 있다. 다음은 널리 이용되는 방법들이다:

* OCaml 패키지 메니저인  OPAM 이용하기
* 이용하는 플랫폼이 제공하는 패키지 메니저 이용하여 설치 하기(Windows, Linux,
  Mac OS X, ...)
* 소스코드로 부터 설치하기

아래의 섹션들에서 각각의 방법들을 어떻게 이용하는지를 알아보도록 하겠다.
OCaml 라이브러리들에 대한 검색과 설치에 대한 더 자세한 정보들은 [libraries](/learn/libraries.html) 페이지에서 찾을 수 있다.

## 멀티플렛폼 패키지 메니저

멀티플렛폼을 지원하는 OCaml 전용 패키지 메니저들에 대해 알아보자:

### OPAM

[OPAM](https://opam.ocaml.org/)은 OCcaml 패키지 메니저로 OCaml 컴파일러와 OCaml 패키지를 설치하는데 추천되는 방법이다. 
메인 OPAM [저장소](https://opam.ocaml.org/packages/)에서는 활발한 활동이 이루어 지고 있으며 사실상 OCaml 패키지들의 마스터 셋으로 이용되고 있다.
OPAM은 다른 설치 방법에서는 제공하지 않는 추가적 기능을 제공하고 있는데 동시에 여러 다른 OCaml버젼을 설치하거나 여러 프로젝트들을 동시에 진행 할때 페키지 의존성의 충돌을 피하기 위해 각각의 프로젝트에 대해 개별적인 패키지 환경을 이용할수 있는 것이 이에 해당한다. 

주의 해야 할 사항으로는 OPAM 자체가 OCaml으로 제작 되어있기 때문에 첫 설치시 OPAM을 설치 하기 위해선 OCaml이 OCaml을 설치하기 위해서는 OPAM이 필요로 하는 문제가 생긴다. 이를 해결하기 위하여 여러 다양한 플랫폼용으로 바이너리 OPAM 패키지가 준비되어 있다. 설치 과정에 대해서는 [이곳](http://software.opensuse.org/download.html?project=home%3Aocaml&package=opam)과 아래의 내용에서 자신의 플렛폼에 해당하는 내용을 읽어 보기 바란다. 또한 가장 최신 [릴리즈](https://github.com/ocaml/opam/release)로 부터 소스를 받아 직접 컴파일 할 수도 있다. 좀 더 자세한 정보는 OPAM [설치 페이지](http://opam.ocaml.org/doc/Install.html)를 참고하기 바란다.

일단 OPAM이 설치 되었으면 우선적으로 `switch`와 `install` 명령어를 이용하게 될것이다. 예를 들면:  

```
opam switch 4.02.1
eval `opam config env`
```
위 명령행들은 OCaml 4.02.1을 컴파일하고 OPAM이 관리하는 장소에 설치를 하게 된다. 두번째 라인은 이 설치 버젼을 이용하겠다는 선언을 해주는 것이다. 만약 여러분의 시스템에 설치 되어있는 기존 버젼의 OCaml을 이용하는 것으로 만족한다면 이 절차는 생략해도 무방하지만 많은 플랫폼에서 기본으로 지원하는 OCaml버젼이 이미 많이 뒤쳐져 있을 것이다.    

다음으로 패키지를 설치해 보자.
```
opam install batteries core
```

이 명령행은 널리 이용되는 Batteries와 Core 표준 라이브러리를 설치해 준다. OPAM의 매인 [저장소](https://opam.ocaml.org/packages/)에서는 수백개가 넘는 다양한 패키지들을 살펴볼수 있으며 [OPAM 메인 페이지](http://opam.ocaml.org/)에서 OPAM의 추가적인 기능을 배울수 있다.

OPAM은 데비안에서 데비안 패키지를 관리하는 Mancoosi 프로젝트(Mancoosi프로젝트는 이외에도 여러가지 기능을 포괄하고있다)를 기반으로 한 CUDF 라이브러리를 기반으로 하고 있다. Unuix, Linux 그리고 맥 OS X 시스템에서 문제 없이 잘 작동하며 윈도우 지원도 곧 가능해질 것이다. OPAM은 [OCamlPro](http://www.ocamlpro.com/)와 [OCaml Labs](http://www.cl.cam.ac.uk/projects/ocamllabs/)에 의해 작성되었고 운영되고 있으며 무료 소프트웨어(free software)이다([상용지원](http://ocamlpro.com) 또한 가능하다). 

### Oasis-DB
[이곳](http://oasis.ocamlcore.org/)을 참고하기 바란다.

### ODB
[이곳](https://github.com/thelema/odb)을 참고하기 바란다.

### ocamlbrew
[이곳](https://github.com/hcarty/ocamlbrew)을 참고하기 바란다.

## 리눅스 배포판

OCaml은 대부분의 리눅스 배포본에서 패키지 메니저를 통해 직접 설치가 가능하다. 여기 대중적인 배포판을 기준으로한 설치 방법이 있다.

### 데비안
OCaml은 [데비안](http://www.debian.org)에서 매우 손쉽게 설치가 가능하다.

```
apt-get install ocaml
```

만약 그래픽 어플리케이션을 개발할 것이 아니라면 대신 `ocaml-nox`를 설치할수도 있다; 그런경우가 아니라면 그냥 `ocaml` 패키지를 설치하도록 하자.

그리고 나선 다음의 페키지들을 설치할것을 추천하는 바이다:

* `ocaml-native-compilers` 네이티브 바이너리를 컴파일 가능하게 해줌 (몇몇 대중적이지 않은 아키텍쳐에서는 제공되지 않는다).
* `ocaml-doc` 리퍼런스 메뉴얼 제공.
* `tuareg-mode`, OCaml 이멕스 모드.
* `ocaml-findlib` 와 `oasis`, 라이브러리(와 그에 따른 의존성)을 쉽게 설치해준다.
* `libpcre-ocaml-dev` PCRE 바인딩.

[데비안 페키지](http://packages.debian.org/search?keywords=ocaml&searchon=all&suite=testing&section=all)를 참고하기 바란다.

### 우분투
[우분투](http://www.ubuntu.com/)는 데비안의 변종으로 데비안과 같은 패키지 메니저를 이용한다. 따라서 데비안에서 설명한 설치 방법이 그대로 적용된다.

[우분투 저장소](http://packages.ubuntu.com/search?keywords=ocaml)에서 OCaml 패키지 리스트를 살펴볼수 있다.

때때로 우분투 공식 저장소가 OCaml과 OPAM 최신 정식 릴리즈보다 많이 뒤쳐져 있을때가 있다. 이럴땐 최신 버젼들을 Anil Madhavapeddy이 운영하는 그의 [PPAs](https://launchpad.net/~avsm) 찾을 수 있다. OPAM 저장소의 테스트 [스크립트](https://github.com/ocaml/opam-repository/blob/master/.travis-ci-install.sh)와 Anil Madhavapeddy의 PPAs를 여러분의 우분투 시스템에서 같이 이용할수 있다. PPAs는 우분투 보안팀에서 리뷰하지 않는 사실을 명심하기 바라며 여러분의 시스템에 PPA를 추가한다는 것은 해당 PPA를 여러분이 개인적인 결정으로 신뢰하기로 했다는 것을 알아두기로 하자. 

### 페도라
[페도라 8](http://fedoraproject.org/)부터, 페도라는 OCaml을 기본 배포판에 적극 지원 하기 시작했다. 최신 OCaml 버젼을 업데이트 해주는 활발한 활동을 하는 페도라 사용자 그룹이 있으며 다양한 종류의 패키지를 지원하고 있다.

OCaml 컴파일러를 설치 하기 위해서는 다음과 같이 한다:
```bash
yum install ocaml
```
'`foo`'라 불리는 Ocaml 라이브러리와 이에 필요한 의존성을 전부 설치하고자 한다면 다음을 실행하면 된다.

```bash
yum install ocaml-foo-devel
```
다음을 실행함으로서 개발 환경을 위한 여러 라이브러리들을 설치 할 수 있다:

```bash
yum install ocaml-camlp4-devel ocaml-ocamldoc ocaml-findlib-devel \
   ocaml-extlib-devel ocaml-calendar-devel
```
OCaml 페키지들 전부를 보고 싶다면 다음을 실행하면 된다:

```bash
yum search ocaml
```
**패키징 규칙과 메일링 리스트**


* 페도라의 [OCaml 패키징 규칙](http://fedoraproject.org/wiki/Packaging/OCaml). 모든 페도라 OCaml 패키지들은 이 규칙을 따라야만 하며 배포되는 모든 OCaml 패키지들은 이러한 표준을 따르고 있다. 
* [OCaml Special Interest Group](http://fedoraproject.org/wiki/SIGs/OCaml).
* [fedora-ocaml-list](https://lists.fedoraproject.org/mailman/listinfo/Ocaml-devel): 페도라, 래드햇 엔터프라이즈 리눅스상에서 OCaml의 이용에 관심이 있는 사람들 모임의 메일링 리스트.

### 젠투
[젠투](http://www.gentoo.org/)에서 기본 툴들을 설치 하려면 `portage` 그룹(e.g._root)의 멤머인 유저로 로그인 상태에서
```bash
emerge ocaml  
```
다른 어떤 패키지들이 실행 가능한지 알아보려면: 
while being logged in as a user that is a member of the `portage` group
(e.g. root).

```bash
emerge -S ocaml 
```

### 수세리눅스
OpenSuSE와 SLES 의 저장소 모두에서 OCaml을 설치 할수 있다:

```
zypper install ocaml
```

### Mageia
[Mageia](http://www.mageia.org/) 배포본에서 OCaml을 지원하고 있다.

OCaml 컴파일러를 설치 하기 위해서는:

```bash
urpmi ocaml-compiler
```
이렇게 설치 되는 ocaml-compiler는 X11 라이브러리에 대한 의존성이 없는 컴파일러이며 만약 module Graphic와 같은 X11 라이브러리에 의존적인 컴파일러를 설치 하려면:

```bash
urpmi ocaml-x11
```
camlp4를 설치하려면:

```bash
urpmi camlp4
```
'`foo`'라는 OCaml 라이브러와 필요한 관련 의존성을 설치 하기 위해서는 다음과 같이 할 수 있다: 

```bash
urpmi ocaml-foo-devel
```
다음을 실행함으로서 기본적인 개발 라이브러리 환경을 설치 할 수 있다: 

```bash
urpmi camlp4-devel ocaml-doc ocaml-findlib-devel \
  ocaml-extlib-devel ocaml-extlib-doc ocaml-batteries-devel \
  ocaml-ounit-devel ocaml-sexplib-devel ocaml-xml-light-devel \
  ocamlmakefile
```
OCaml 패키지 리스트를 확인 하려면:

```bash
urpmq --list | grep ocaml
```
**패키지 규칙**

* Mageia의 [OCaml 패키지 규칙](https://wiki.mageia.org/en/OCaml_policy). 모든 Mageia OCaml 패키지들은 이 규칙을 따라야만 하며 배포되는 모든 OCaml 패키지들은 이러한 표준을 준수 하고 있다.

## 윈도우즈

윈도우즈상에서는 다음의 두가지 방법으로 OCaml을 이용할 수 있다: ygwin을 필요로 하는 OCaml 공식 배포버젼과 OCamlPro에서 제공하는 Cygwin 없이 실행 가능한 바이너리 배포버젼인 OCPWin을 이용할수 있다.

### Cygwin에서 OCaml 이용하기

현재 세가지 버젼의 마이크로소프트 윈도우즈용 OCaml이 이용 가능하다. 자세한 사항은 [이식성 관련 이슈](learn/poratability.html)의 리스트나 [윈도우 릴리즈 노트](http://caml.inria.fr/pub/distrib/ocaml-4.00/notes/README.win32)를 참고하기 바란다. 

* [Cygwin 기반 네이티브 Win32 포트 (4.00.1)](http://protz.github.io/ocaml-installer/). 설치파일 제공. 간단한 그래픽 유저 인터페이스를 포함하는 대화형 화면 지원. 일부 기능은 Cygwin 환경을 필요로 함 (인스톨러에 포함). 컴파일러는 Win32 실행 파일로 생성되는 바이너리는 그 실행을 위해 Cygwin 환경을 필요로 하지 않음. 
* 마이크로소프트 기반 네이티브 Win32 포트. 바이너리 파일을 아직 지원 하지 않음; 소스를 다운하여 컴파일 하여야 함. 배포되는 소스에 필요한 툴들(Cygwin 요구)과 다운 받을수 있는 링크 그리고 설명이 있음 (README.win32).
  - 32비트/64비트를 지원하는 설정;
  - 윈도우즈 7 sdk를 이용한 마이크로소프트 툴셋 제공;
  - XP/Windows 7/Windows 8.1에서 테스트 됨.
  - 윈도우즈 8.1에서
    - Cygwin chmod 0600 appears broken : comment L367 of Makefile.nt (@chmod -w utils/config.ml);
    - This same problem with Cygwin chmod also affects ssh configuration setup (may affect interaction with github projects). See [this page](http://superuser.com/questions/397288/using-cygwin-in-windows-8-chmod-600-does-not-work-as-expected) for a suggested workaround.
* [Cygwin](http://cygwin.com/)기반 포트. Cygwin이 필요. 그래픽 유저 인터페이스는 제공되지 않음. 컴파일러가 생성하는 실행파일은 Cygwin을 필요로 함.
 프리컴파일 바이너리는 Cygwin distribution의 일부분임; Cygwin의 `setup`툴을 이용하여 설치 할수 있음. 다른 방법으로 소스를 다운받아 Cygwin에서 컴파일 할수 있음.

라이브러리를 설치 하려면 [wodi](http://wodi.forge.ocamlcore.org/)나 OPAM을 이용하면 됨. 

### OCPWIN, 윈도우즈 용 OCaml 독자 바이너리 

OCPWin은 (독립된) 윈도우즈용 바이너리 설치 파일이다. 32비트와 64비트 윈도우즈 플랫폼 둘다를 지원하며 바이트코드와 네이티브 코드 어플리케이션 둘다를 다른 추가적인 소프트웨어 설치 없이 바로 윈도우즈 터미널에서 컴파일 할수 있다. 컴파일러 일부분이 재배포 되지 않는 이상 사용과 비상용 이용에 대한 라이센스를 둘다 지원한다. 바이너리 인스톨러는 OCaml 4.01.0을 제공하고 있다. 윈도우즈 지원을 위한 편리한 추가적인 기능들이 OCaml에 포함 되어 있다.    

*알림: OCPWin의 링크는 현재 OCPWin으 문제로 인하여 삭제 되어있으며 문제가 해결되기를 기다리고 있다.* 

## 맥 OS X
맥 OS X에서는 다음의 각기 다른 방법으로 기본 패키지를 설치 할수 있다: Homebrew 패키지 매니지먼트 시스템과 OPAM을 이용하는 방법(권장); 핑크(Fink)를 이용한 방법; 맥포트(MacPorts)를 이용한 방법; 소스코드로부터 직접 빌드하는 방법. 이 각각의 방법 모두 기본적으로 OS X 개발 툴이 설치 되어있어야 하며 - 그 이상의 요구 조건에 대해서는 아래에 설명해 두었다. 

###  Inria의 바이너리 패키지

[Inris는 Ocaml 4.02.X 버젼에 대해서 맥오에스 바이너리를 더 이상 제공하지 않는다](http://caml.inria.fr/download.en.html). 이전 버젼의 Ocaml 인텔 디스크 이미지는 [다운로드](../releases/)링크에서 구할 수 있다. 

해당 바이너리 패키지는 커맨드라인 툴만을 제공하고 있으며 어떤 그래픽기반 어플리케이션도 제공하지 않는다. 

### Homebrew

[Homebrew](http://brew.sh/)는 새로운 맥 OS X의 패키지 매니지 먼트 시스템으로 큰 규모의 커뮤니티를 구축하고 있다.  Homebrew를 [설치](https://github.com/Homebrew/homebrew/wiki/Installation)하기 위해서는 bash나 zsh과 xcode의 커맨드 라인 툴이 필요하다.

Homebrew를 설치한 후, 다음의 명령어로 OCaml을 설치 할수 있다.
멸령어:

```bash
brew install ocaml
```

OCaml 패키지 매니저인  [OPAM](http://opam.ocaml.org/)을 
You can then install [OPAM](http://opam.ocaml.org/), the
OCaml package manager, which will give you access to all its
[packages](http://opam.ocaml.org/packages/) by running:

```bash
brew install opam
```

###  핑크(Fink)
[핑크(Fink)](http://fink.sourceforge.net/ "Fink")는 OS X에서 가장 널리 퍼져있는 패키지 관리 시스템이며 데비안의 패키지 관리 시스템에 기반을 하고 있다. 핑크는 다음의 [소스 릴리즈](http://fink.sourceforge.net/download.srcdist.php?phpLang=en)에서 다운받아 빌드 할수 있다(핑크를 빌드하기 이전에 OS X 개발툴이 먼저 설치 되어 있어야 한다). 핑크가 설치된 후 배포 트리의 [unstable branch](http://fink.sourceforge.net/faq/usage-fink.php#unstsable)로 설정되어야 한다. -- OCaml 패키지는 이 unstable branch에 존재 한다.

일단 핑크가 설치 된후, 다음의 [패키지들을 설치](http://fink.sourceforge.net/doc/users-guide/index.php) 하기 바란다.

* `ocaml` labltk를 포함한 OCaml 툴들의 기본적인 설치 
* `lablgl` OpenGL용 OCaml 인터페이스 
* `lablgtk` gtk+용 OCaml 인터페이스 
* `ledit` 터미널에서 toplevel을 이용할때 편리하게 해주는 OCaml용 라인 에디터(옵션 사항)

핑크에서 OCaml 패키지를 빌드하기 위해선 여러 다른 패키지들을 필요로 하고 있다. 하지만 대부분 자동으로 설치 되게 된다. 

### 맥포트(MacPorts)
이전에는 다윈포트(DarwinPorts)라고도 불린 [맥포트(MacPorts)](http://www.macports.org/)는 BSD의 포트 시스템에 기반을 한 맥 OS X의 패키지 관리 시스템이다. 맥포트를 [인스톨](http://www.macports.org/?page_id=48)을 설치하기 이전에 OS X 개발툴이 설치 되어 있어야 한다. 맥포트로 다음의 패티지들을 다운로드 하여 설치 할 수 있다: 

* `ocaml` labltk를 초함한 OCaml 툴들의 기본적인 설치 
* `lablgl` OpenGL용 OCaml 인터페이스 
* `lablgtk` gtk+용 OCaml 인터페이스 
* `lablgtk2` gtk+ 2.x용 OCaml 인터페이스
* `cryptokit` 여러 암호화 기능을 위한 OCaml 인터페이스 
* `ocaml-mode.el` OCaml 프로그램을 위한 EMACS 매이저 모드 
* `tuareg-mode.el` OCcaml 프로그램 편집을 위한 GNU Emacs/XEmacs 매이저 모드

### 소스로 부터 설치하기
불해히도 핑크와 다윈포트용 패키지들에는 MArkus Mottl의 PCRE_Ocaml 라이브러리나 Stolpmann의 findlib 시스템과 같은 여러 유용한 OCaml 콜렉션이 아직 포함되어 있지 않다. 이러한 패키지들을 이용하기 위해 소스로부터 빌드를 해야만 한다.  

다음의 패키지들이 설치를 통해 유용하게 이용될 수 있다: 

* [The OCaml 소스.](../releases/)
* [Findlib](http://www.camlcity.org/archive/programming/findlib.html), OCaml 라이브러리 매니지먼트 시스템.
* [Batteries](http://batteries.forge.ocamlcore.org/), 기본 OCaml 라이브러리들을 개선하고 확장한 라이브러리 콜렉션.
* [PCRE-OCaml](https://github.com/mmottl/pcre-ocaml), OCaml에서 이용가능한 Perl 호환 정규표현식 라이브러리([PCRE 라이브러리](http://www.pcre.org/) 설치를 필요로 한다). 
* [OCamlMakefile](https://github.com/mmottl/ocaml-makefile) OCaml 프로젝트의 makefile을 손쉽해 해주는 도구 

만약 OpenGL, Gtk+ 혹은 Gtk+2와 같은 추가적인 컴포넌트가 이미 설치 되어있다면 
[lablgl](http://wwwfun.kurims.kyoto-u.ac.jp/soft/olabl/lablgl.html)나 
[lablgtk](http://wwwfun.kurims.kyoto-u.ac.jp/soft/olabl/lablgtk.html)등과
같은 패키지 또한 빌드 될수 있다. 가장 유연한 해법으로는 핑크를 이용하여 필수 디펜던시들을
설치한후 소스 배포본으로부터 OCaml 패키지를 빌드 하는 것이다. 

###  OS X에서 labltk 이용하기 
OS X에서 libltk를 이용하는 데는 여러가지 방법이 있다. Tcl/TK 라이브러리를
다운로드하여 직접 빌드하는 방법도 있지만, 이보다 더 간편한 방법이 두가지 있는데:
[핑크(Fink)](http://fink.sourceforge.net/)을 이용하여 Tcl/Tk를 설치하는 방법과
[Tcl/Tk Aqua](http://tcltkaqua.sourceforge.net/) 프래임워크를 이용하는 방법이다.
이 둘사이에는 OCaml과 labltk를 설치하기 이전에 여러분들이 반드시 고려해야할 중요한
차이점이 있다:

1. 핑크 라이브러리는 labtk를 이용하는 프로그램을 구동하기 위해서 X11을 필요로 한다.
반면 Tcl/Tk Aqua 라이브러리는 OS X 네이티브 어플리케이션 처럼 (외형적으로도 네이티브
어플리케이션의 Look and feel을 제공한다) 작동하게 된다.

2. 지금 이 글을 쓴 시점을 기준으로 보면, 만약 labltk 어플리케이션이 Tcl/Tk Aqua
라이브러리와 함께 빌드 되었을때 반드시 네이티브 OS X 어플리케이션으로 (추가적인 빌드 과정을
요구함) 빌드 되어야만 한다. 만약 바이트 코드로된 이식이 편한 코드를 원한다거나 labltk가
활성화된 toplevel의 대화식(interactive) 환경을 원한다면 핑크 라이브러리를 *이용해야만( 한다.


#### 핑크(fink) 라이브러리 설치하기
핑크가 일단 [설치된 후 문제없이 설정까지 마쳤다면](http://fink.sourceforge.net/doc/index.php?phpLang=en)
다음의 명령행으로 Tcl/Tk 라이브러를 설치한다; `fink install tcltk tcltk-dev tcltk-shlibs`.
빌드와 인스톨이 다 될때 까지 약간의 시간이 소료된다. 일단 다 되면, OCaml 설정 스크립트가 labltk를
빌드하기 위한 라이브러리와 해더파일을 찾게 된다 (설치된 핑크는 /sw 디렉토리에 labltk를 설치하게 된다).
OCaml이 표준 빌드를 실행함으로서 labltk를 빌드 할 수도 있다. 

##### Tcl/Tk Aqua 라이브러리 설치하기
이 프래임워크는 OS X 10.4 이후 버젼부터 제공되기 시작했다. 다음의 플래그를 이용하여
OCaml 빌드를 설정하기 바란다. 


```bash
./configure -tkdefs \
  "-I/Library/Frameworks/Tcl.framework/Headers \
  -I/Library/Frameworks/Tk.framework/Headers" \
  -tklibs "-framework Tcl -framework Tk" 
```
이제 OCaml을 빌드함으로서 Tcl/Tk Aqua 라이브러리를 이용하는 labltk 까지
함께 빌드 되게 된다. 

위에 언급했듯이, 
As mentioned above, any programs using labltk must be compiled using
`ocamlopt`, and an additional step must be performed before the
application can be used. For example, with the simple program,
`hello.ml`:

```ocaml
open Tk;;
let hello () =
  print_endline "Hello!"; flush stdout in
let top = openTk () in
let hb =
Button.create ~text:"Hello" ~command:hello top in
pack [hb];
mainLoop ()       
```
One would compile this program with the command
`ocamlopt -o hello -I +labltk labltk.cmxa     hello.ml`

Now, to make the program work properly, one must perform one of two
additional steps: adding a resource fork to the executable, or building
a Mac OS X .app structure.

To add a resource fork, one needs to use the program `Rez`, included in
the OS X Developer tools. This can be done with the following command:

```bash
/Developer/Tools/Rez -t APPL -o hello ~/dev/mac.r \
  -i /Library/Frameworks/Tcl.framework/Headers \
  -i /Library/Frameworks/Tk.framework/Headers   
```
Where mac.r is a Rez source file. It is part of the
[FLTK](http://www.fltk.org/) distribution. This will add the required
resource fork to the hello application. The program can be run either by
typing `hello` at the command line or by double-clicking the app's icon
(note that if it is launched by double-clicking, hello will send its
output to the OS X console rather than the terminal).

Unfortunately, files with resource forks can present a problem in that
utilities like `cp, mv, tar`, etc. will strip the resource fork from the
file, breaking the application. To aleviate this problem, one can build
an OS X application bundle to wrap the compiled executable.

To do this, after compiling with
`ocamlopt -o hello -I     +labltk labltk.cmxa hello.ml`, the following
steps will build the bundle:

```bash
mkdir hello.app
mkdir hello.app/Contents
mkdir hello.app/Contents/MacOS
mv hello hello.app/Contents/MacOS  
```
Next, create a file `hello.app/Contents/Info.plist` with the following
contents:

```
<?xml version="1.0" encoding="UTF-8"?>
<plist version="1.0">
 <dict>
   <key>CFBundleExecutable</key>
   <string>hello</string>
 </dict>
</plist>        
```
The hello application can now be run from the command line by typing
`open hello.app`, or by double-clicking on the app's icon (again, this
will send hello.app's output to the console).

###  Tips
**Documentation.** To get quick access to the documentation of a module
(whatever the editor you use), use
[Quicksilver](http://qsapp.com/) to index the libref/
directory of ocaml's documentation. Since ocamldoc generates the
documentation of a module M in a file M.html, you can access it by
invoking Quicksilver, type an abbreviation of the module's name you want
and hit return to get its html file loaded in your preferred browser.

**Profiling.** To profile native-code programs *do not* compile them
with the option -p (this is unsupported). Instruments is included with XCode, 
but not in the Command Line Tools. Start it with the Time Profiler template and
then run the native code ocaml executable. Alternatively, iprofiler is a command
line interface to it.

OCaml builtins will show up in cleartext but user-defined functions will be replaced 
by autogenerated symbols. In principle, more function names should show up in the profiles 
if you compile with `-g`, but this does not seem to work. Therefore, time profiling on 
OS X is currently of limited use.

## FreeBSD
[FreeBSD](http://www.freebsd.org/)는 오랜시간동안 OCaml을 잘 지원해 왔다. 대부분의 인기있는 플랫폼 (i386, amd64, powerpc, sparc64)용으로 코어 언어와 보조 라이브러리, 문서, 예제 그리고 개발툴을 설치할수 있는 손쉽게 이용 가능한 패키지들이 제공되어 왔다. 새로운 OCaml 어플리케이션과 라이브러리를 쉽게 추가해주는 프래임워크도 준비 되어있다.

OCaml 컴파일러를 패키지로부터 설치하기 위해서는 다음과 같이 하면된다:

```bash
pkg_add -r ocaml
```
혹은
OCaml을 X11 의존성 없이 설치하고자 원한다면(예, headless 서버에 디플로이 원하는 경우)

```bash
pkg_add -r ocaml-nox11
```

개발 문서, 예제 그리고 이멕스용 편집 마크로를 설치하려면 `ocaml-doc`, `ocaml-examples` 그리고 `ocaml-mode.el` 패키지를 설치하면 된다.

동일한 패키지들이 port 시스템을 통해서도 설치될 수 있다. ports 시스템안의 `devel` 카테고리안에는 많은 수의 라이브러리들이 존재하고 있을 뿐만 아니라 각각의 개별적인 토픽 카테고리안에도 여러 패키지들이 제공되고 있다.

## 소스로부터 설치하기

[원하는 OCaml 소스](/releases/)를 다운한 후 (혹은 서브버젼이나 깃을 이용하여 [개발 버젼](/releases/svn.html)을 가져다) 그곳에 포함된 설명을 참고 하면 된다. 
