<!-- ((! set title OCaml 튜토리얼 !)) ((! set learn !)) -->
<!-- {{! input template/macros.mpp !}} -->

# OCaml 튜토리얼

#### 여러분의 도움이 필요 합니다.
아래의 튜토리얼들 중 많은 부분이 업데이트를 필요로 하거나 새로운 주제의 추가를 필요로 하고 있습니다. 본 프로젝트의 [GitHub](https://github.com/ocaml/ocaml.org) 저장소를 방문하시어 컨트리뷰션을 하실수 있습니다; 또한 새로운 튜토리얼에 대한 제안이나 요청에 대해서는 저장소의 이슈 트래커를 이용해주시면 됩니다. 감사합니다! 

((! get begin_two_columns !))

* [기본사항](basics.ko.html) 
* [OCaml 프로그램의 구조](structure_of_ocaml_programs.ko.html)
* [모듈](modules.ko.html)
* 맵(Maps) (Dictionaries) - [en](map.html)
* 셋(Sets) - [en](set.html)
* 해쉬 테이블 - [en](hashtbl.html)
* 기본 컨테이너들의 비교  - [en](comparison_of_standard_containers.html)
* 데이타 타입과 매칭 — [en](data_types_and_matching.html)
* OCaml 포인터 - [en](pointers.html)
* 널 포인터, 어설트(Assert), 경고(Warning) — [en](null_pointers_asserts_and_warnings.html)
* 함수형 프로그래밍 — [en](functional_programming.html)
* [If 문, 루프, 재귀](if_statements_loops_and_recursion.ko.html)
* 레이블 — [en](labels.html)
* 일반 오류 메시지 — [en](common_error_messages.html)
* OCaml 프로그래밍 스타일 — [en](guidelines.html)
* 텍스트 포멧과 래핑- [en](format.html)
* OCaml을 이용한 99문제 (풀이) - [en](99problems.html)
* [OCamlbuild](ocamlbuild/)

((! get second_of_two_columns !))

* 객체 — [en](objects.html)
* Gtk 소개 — [en](introduction_to_gtk.html)
* 가비지 콜렉션 — [en](garbage_collection.html)
* 성능과 프로파일링 — [en](performance_and_profiling.html)
* C 라이브러리 호출하기 — [en](calling_c_libraries.html)
* 포트란 라이브러리 호출하기 — [en](calling_fortran_libraries.html)
* OCaml과 웹 — [en](ocaml_and_the_web.html)
* 표준 라이브러리 예제 — [en](standard_library_examples.html)
* OASIS 이용하여 OCaml 프로젝트 세팅하기 - [en](setting_up_with_oasis.html)
* OCaml 프로젝트 컴파일하기 — [en](compiling_ocaml_projects.html)
* 명령행 인자 — [en](command-line_arguments.html)
* 파일 조작 — [en](file_manipulation.html)
* [Camlp4 3.10](camlp4_3.10/)
* 파일 이름과 확장자 - [en](filenames.html)
* 스트림 - [en](streams.html)
* 스트림 익스프래션 - [en](stream_expressions.html)
* [_감사의 말_](../../contributors.html#Oldercontributorstothetutorials)

((! get end_two_columns !))


## 외부 자료들

###  직접 따라하며 배우기

* [Try OCaml Online](http://try.ocamlpro.com/) (by OCamlPro) allows
 you to immediately start learning OCaml in your browser, without
 installing it. Compiled as a single Javascript page, it gives you
 the full power of OCaml, even when your are disconnected from the
 network.
* [PLEAC-OCaml](http://pleac.sourceforge.net/pleac_ocaml/) provides
 OCaml solutions to the complete set of problems originally posed in
 the very successful Perl Cookbook. OCaml is one of only 3 languages
 for which the full set of solutions has been provided.
* [Rosetta](http://rosettacode.org/wiki/Category:OCaml) is a
 programming chrestomathy site. It provides solutions to the same
 task in many languages. Currently there are few tasks with OCaml
 solutions provided, but perhaps you would like to add new solutions.

###  OCaml 튜토리얼

* [OCaml 시스템](http://caml.inria.fr/pub/docs/manual-ocaml/) (by
 Inria) is the official user's manual. The first part provides an
 introduction to the core language, objects and classes, and modules.
 Previous versions are [here](http://caml.inria.fr/pub/docs/).
* [How to wrap C functions to
  OCaml](http://www.linux-nantes.org/~fmonnier/OCaml/ocaml-wrapping-c.html)
  (by Florent Monnier) explains in an understandable way how to write C
  stubs to call C functions from OCaml and back. It features a lot of
  examples.
* [OCaml for scientific
 computation](http://www.southampton.ac.uk/~fangohr/software/ocamltutorial/)
 (by Thomas Fiscbacher), covers a broad sample of OCaml, from the
 basics to the C api.

###  WikiBooks에 있는 OCaml

* [fr.wikibooks.org/wiki/OCaml](http://fr.wikibooks.org/wiki/OCaml)
 (in French):
 Introduction on functional programming using OCaml.
* [fr.wikiversity.org/wiki/Premiers_pas_en_OCaml](http://fr.wikiversity.org/wiki/Premiers_pas_en_OCaml)
 (in French):
 The basics of the OCaml language.

###  도구들의 튜토리얼 모음
There are also tutorials that can be useful to learn how to use popular
tools and libraries.

* [Camlp4
 Tutorial](http://ambassadortothecomputers.blogspot.com/p/reading-camlp4.html)
 (by Jake Donham), to build syntax extensions for OCaml with Camlp4.
* [OCamllex
 Tutorial](http://plus.kaist.ac.kr/~shoh/ocaml/ocamllex-ocamlyacc/ocamllex-tutorial/)
 (by SooHyoung Oh), on how to create lexers using the `ocamllex` tool
 of the standard distribution.
* [OCamlyacc
 Tutorial](http://plus.kaist.ac.kr/~shoh/ocaml/ocamllex-ocamlyacc/ocamlyacc-tutorial/)
 (by SooHyoung Oh), on how to create parsers using the `ocamlyacc`
 tool of the standard distribution.
* [LablGTK 2.0
 Tutorial](http://plus.kaist.ac.kr/~shoh/ocaml/lablgtk2/lablgtk2-tutorial/)
 (by SooHyoung Oh), on how to create graphical applications with the
 LablGTK library.
* [Camlp5](camlp5.html)
* [A Guide to Extension Points in OCaml](http://whitequark.org/blog/2014/04/16/a-guide-to-extension-points-in-ocaml/)
  (by whitequark), on using PPX, the syntax extensions API that superseded camlp4.

###  Coming From Another Language

These tutorials help learn OCaml from the perspective of being familiar
with another language.

* [Beyond functional programming in Haskell: an introduction to
 OCaml](http://www.cs.uu.nl/wiki/pub/Stc/BeyondFunctionalProgrammingInHaskell:AnIntroductionToOCaml/ocaml.pdf)
* [OCaml for Haskellers](http://blog.ezyang.com/2010/10/ocaml-for-haskellers/)

###  Advanced Tutorials & Articles

* [메뉴얼](http://caml.inria.fr/pub/docs/manual-ocaml/)
* [Detecting use cases for GADTs in OCaml](http://mads-hartmann.com/ocaml/2015/01/05/gadt-ocaml.html),
  (by Mads Hartmann), on using generalized algebraic data types in writing interpreters.
