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
OPAM은 다른 설치 방법에서는 제공하지 않는 추가적 기능을 제공하고 있는데 동시에 여러 다른 OCaml버젼을 설치하거나 각각의 프로젝트에서 페키지 의존성의 충돌을 피하기 위한 여러 유니버션 페키지가 이에 해당한다. 

주의 해야 할 사항으로는 OPAM 자체가 OCaml으로 제작 되어있기 때문에 첫 설치시 문제가 생길 수 있다. 이를 해결하기 위하여 여러 다양한 플랫폼용으로 바이너리 OPAM 패키지가 준비되어 있다. 설치 과정에 대해서는 [이곳](http://software.opensuse.org/download.html?project=home%3Aocaml&package=opam)과 아래의 내용에서 자신의 플렛폼에 해당하는 내용을 읽어 보기 바란다. 또한 가장 최신 [릴리즈](https://github.com/ocaml/opam/release)로 부터 소스를 받아 직접 컴파일 할 수도 있다. 좀 더 자세한 정보는 OPAM [설치 페이지](http://opam.ocaml.org/doc/Install.html)를 참고하기 바란다.

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

### 젠투(Gentoo)
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

* [Cygwin 기반 네이티브 Win32 포트 (4.00.1)](http://protz.github.io/ocaml-installer/). A self
 installer. The interactive loop comes with a simple graphical user
 interface. Some features require the Cygwin environment, which the
 installer can fetch for you. However, the compilers are true Win32 executables,
 and binaries they generate do not require Cygwin to run too.
* 마이크로소프트 기반 네이티브 Win32 포트. No binary distributions
 available yet; download the source distribution and compile it. Build
 instructions including required tools (Cygwin required) and download
 links in the source distribution (README.win32).
  - Configurations supported include 32-bit/64-bit;
  - Microsoft toolset support provided by Windows 7 SDK;
  - Tested with XP/Windows 7/Windows 8.1.
  - On Windows 8.1
    - Cygwin chmod 0600 appears broken : comment L367 of Makefile.nt
       (@chmod -w utils/config.ml);
    - This same problem with Cygwin chmod also affects ssh
      configuration setup (may affect interaction with github
      projects). See [this page](http://superuser.com/questions/397288/using-cygwin-in-windows-8-chmod-600-does-not-work-as-expected)
      for a suggested workaround.
* [Cygwin](http://cygwin.com/)기반 포트. Requires Cygwin. No
 graphical user interface is provided. The compilers generate
 executables that do require Cygwin. The precompiled binaries are
 part of the Cygwin distribution; you can install them using the
 Cygwin `setup` tool. Alternatively, download the source distribution
 and compile it under Cygwin.

To install libraries, you may use
[Wodi](http://wodi.forge.ocamlcore.org/) or OPAM.

### OCPWIN, 윈도우즈 용 OCaml 독자 바이너리 

OCPWin is a self-contained binary
distribution of OCaml for
Windows. It supports both 32-bit and 64-bit Windows platforms, and can
compile both bytecode and native code applications, directly from a
Windows terminal, without installing other software. The license
agreement allows both commercial and non-commercial use, as long as
the compiler parts themselves are not redistributed. A binary
installer is provided for OCaml 4.01.0. Some additional features have
been added to OCaml for better support of Windows.

*Note: The link for OCPWin has been removed due to an issue waiting to be solved.*

## 맥 OS X
On Mac OS X, there are, at least for the base package, a few different
ways to go: Install Homebrew package management system and use OPAM (recommeneded); Install via Fink;
Install via MacPorts; or build it manually from
sources. For each of these approaches, you will need to have at least
the OS X developer tools installed — any other requirements will be
discussed below.

###  Inria의 바이너리 패키지

[Inria stopped supporting MacOS binaries for OCaml 4.02.X](http://caml.inria.fr/download.en.html).
For earlier versions of OCaml  Intel disk image images follow the [download](../releases/) link.

The package only includes command-line tools and does not include any
graphical applications.

### Homebrew

[Homebrew](http://brew.sh/) is a new and upcoming package management
system for Mac OS X and has a very large community.
Homebrew requires the command line tools for Xcode and either bash or zsh to
[install](https://github.com/Homebrew/homebrew/wiki/Installation).

After installing Homebrew, you can install OCaml by issuing the following
command:

```bash
brew install ocaml
```

You can then install [OPAM](http://opam.ocaml.org/), the
OCaml package manager, which will give you access to all its
[packages](http://opam.ocaml.org/packages/) by running:

```bash
brew install opam
```

###  핑크(Fink)
[Fink](http://fink.sourceforge.net/ "Fink") is the most prevalent
package management system for OS X, and is based on Debian's package
management system. Fink can be installed by downloading and building the
[source
release](http://fink.sourceforge.net/download/srcdist.php?phpLang=en)
(you will need to have the OS X Developer Tools installed before
building Fink). After Fink is installed, it must be [configured to use
the unstable
branch](http://fink.sourceforge.net/faq/usage-fink.php#unstable) of the
distribution tree -- this is where the OCaml packages reside.

Once Fink is installed, you can [use it to
install](http://fink.sourceforge.net/doc/users-guide/index.php) the
following packages:

* `ocaml` The basic installation of the ocaml tools including labltk.
* `lablgl` The OCaml interface to OpenGL
* `lablgtk` The OCaml interface to gtk+
* `ledit` An optional line editor for OCaml to make it easier to work
 with the interactive toplevel in the terminal.

It is likely that Fink will need to download and install a number of
other packages required to build the OCaml packages, but this will occur
mostly automatically.

### 맥포트(MacPorts)
[MacPorts](http://www.macports.org/), formerly known as DarwinPorts, is
a package management system for Mac OS X based on the BSD ports system.
You will need to have the OS X Developer Tools installed before
[installing](http://www.macports.org/?page_id=48) MacPorts. MacPorts can
be used to download and build the following packages:

* `ocaml` The basic installation of the ocaml tools including labltk.
* `lablgl` The OCaml interface to OpenGL
* `lablgtk` The OCaml interface to gtk+
* `lablgtk2` The OCaml interface to gtk+ 2.x
* `cryptokit` An OCaml interface to several cryptographic functions.
* `ocaml-mode.el` An EMACS major mode for editing OCaml programs.
* `tuareg-mode.el` A GNU Emacs/XEmacs major mode for editing OCaml
 programs.


### Building from sources
Unfortunately, the packages available for both Fink and DarwinPorts
don't yet include some of the more useful additions to the OCaml
collection, such as Markus Mottl's PCRE-Ocaml library or Stolpmann's
findlib system. In order to get those packages, one must currently build
them from source.

The following packages are the most beneficial to install:

* [The OCaml source distribution.](../releases/)
* [Findlib](http://www.camlcity.org/archive/programming/findlib.html),
 an OCaml library management system.
* [Batteries](http://batteries.forge.ocamlcore.org/), a collection of
 libraries that extend and improve upon the OCaml Standard Library
* [PCRE-OCaml](https://github.com/mmottl/pcre-ocaml), a
 library for working with Perl Compatible Regular Expressions in
 OCaml (this will require you to build [the PCRE
 library](http://www.pcre.org/) as well).
* [OCamlMakefile](https://github.com/mmottl/ocaml-makefile) which
 makes it easy to create makefiles for OCaml projects.

If additional components, such as OpenGL and Gtk+ or Gtk+2 have already
been installed, packages such as
[lablgl](http://wwwfun.kurims.kyoto-u.ac.jp/soft/olabl/lablgl.html),
[lablgtk](http://wwwfun.kurims.kyoto-u.ac.jp/soft/olabl/lablgtk.html),
etc. can be built as well. The most flexible solution for doing this is
often using Fink to install the required dependencies, and build the
OCaml packages from source distributions.


###  Using labltk with OS X
There are a couple of different ways one can go if they wish to use
labltk with OS X. One could download and build the Tcl/Tk libraries
themselves and use those libraries. However, there are two easier ways
to proceed, using [Fink](http://fink.sourceforge.net/) to install
Tcl/Tk, or using the [Tcl/Tk Aqua](http://tcltkaqua.sourceforge.net/)
Framework. There are two very important distinction between the two that
one needs to consider before installing OCaml and labltk:

1. The fink libraries require X11 to be running when any program using
 labltk is executed, while the Tcl/Tk Aqua libraries will execute
 (and look and feel) like a native OS X application
1. As of the time of writing this, it appears as if labltk applications
 built with the Tcl/Tk Aqua libraries *must* be built as native OS X
 applications (and require an extra step at build time). If one
 requires the portability of bytecode, or needs the interactive
 environment of a labltk enabled toplevel, then they *must* use the
 fink libraries.

####  Installing the fink libraries
Once Fink is [installed and
configured](http://fink.sourceforge.net/doc/index.php?phpLang=en),
install the Tcl/Tk libraries with the command
`fink install tcltk tcltk-dev     tcltk-shlibs` and wait for the build
and install process to compete. Once this is done, OCaml's configure
script should be able to locate the libraries and header files required
to build labltk (provided fink is set up to install its packages in the
/sw directory). Running the standard OCaml build will also build labltk.

#####  Installing the Tcl/Tk Aqua libraries
This framework comes with OS X 10.4 and later. Configure the OCaml build
by using the following flags:

```bash
./configure -tkdefs \
  "-I/Library/Frameworks/Tcl.framework/Headers \
  -I/Library/Frameworks/Tk.framework/Headers" \
  -tklibs "-framework Tcl -framework Tk" 
```
Now building OCaml will also build labltk using the Tcl/Tk Aqua
libraries.

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
[FreeBSD](http://www.freebsd.org/) had a great support for OCaml
development for a long time. There are easy to use packages available
for most popular platforms (i386, amd64, powerpc, sparc64) for both the
core languages and supplimentary libraries, documentation, examples and
development tools. There is a framework available to make adding new
ocaml application and libraries easy.

To install the OCaml compiler from packages, do:

```bash
pkg_add -r ocaml
```
or

```bash
pkg_add -r ocaml-nox11
```
to install OCaml without X11-dependent libraries (e.g. to deploy on a
headless server).

To install the developer documentation, examples and emacs editing
macros use the `ocaml-doc`, `ocaml-examples` and `ocaml-mode.el`
packages.

The same packages can be installed via the port system. There is a
large set of libraries available in the `devel` category of the ports
system as well as in the specific topic-related categories.

## From Source

Download the [source for your preferred OCaml release](/releases/)
(or take the [development version](/releases/svn.html) using
Subversion or Git) and follow the instructions included therein.
