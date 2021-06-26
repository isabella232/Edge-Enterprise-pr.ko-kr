---
title: 정규식 2 구문
ms.author: comanea
author: dan-wesley
manager: seanlyn
ms.date: 06/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 정규식 2 구문
ms.openlocfilehash: 5d7026a034300e098497c63911f7516f72877c5d
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617318"
---
# <a name="regular-expression-2-re2h-syntax"></a><span data-ttu-id="0644f-103">정규식 2(re2.h) 구문</span><span class="sxs-lookup"><span data-stu-id="0644f-103">Regular Expression 2 (re2.h) syntax</span></span>

<span data-ttu-id="0644f-104">정규식은 문자열 세트를 설명하기 위한 표기법입니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-104">Regular expressions are a notation for describing sets of character strings.</span></span> <span data-ttu-id="0644f-105">문자열이 정규식으로 설명된 집합에 있을 때 정규식이 문자열과 일치한다고 종종 말합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-105">When a string is in the set described by a regular expression, we often say that the regular expression matches the string.</span></span>

<span data-ttu-id="0644f-106">가장 간단한 정규식은 단일 리터럴 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-106">The simplest regular expression is a single literal character.</span></span> <span data-ttu-id="0644f-107">*\*+?()|* 과 같은 메타 문자를 제외하고 문자는 자신과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-107">Except for the metacharacters like *\*+?()|*, characters match themselves.</span></span> <span data-ttu-id="0644f-108">메타 문자를 일치 시키려면 백 슬래시로 이스케이프하세요. \+는 리터럴 더하기 문자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-108">To match a metacharacter, escape it with a backslash: \+ matches a literal plus character.</span></span>

<span data-ttu-id="0644f-109">두 개의 정규식을 변경하거나 연결하여 새 정규식을 형성할 수 있습니다.*e<sub>1</sub>* 이 _s_ 및 \* e <sub>2</sub>와 일치하는 경우 *는 _t_와 일치하고 *e<sub>1</sub>* | \* e <sub>2</sub>* 은 _ s<와 일치합니다. _ 또는 _t_, *e<sub>1</sub>* \* e <sub>2</sub> \*은 _ st_와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-109">Two regular expressions can be altered or concatenated to form a new regular expression: if *e<sub>1</sub>* matches _s_ and *e<sub>2</sub>* matches _t_, then *e<sub>1</sub>* | *e<sub>2</sub>* matches _s_ or _t_, and *e<sub>1</sub>* *e<sub>2</sub>*  matches _st_.</span></span>

<span data-ttu-id="0644f-110">메타 문자 _ \* _, _ + _ 및 _? _</span><span class="sxs-lookup"><span data-stu-id="0644f-110">The metacharacters _\*_ , _+_ , and _?_</span></span> <span data-ttu-id="0644f-111">반복 연산자입니다: *e<sub>1</sub>*_ \*_ 는 0개 이상의 (아마도 다른) 문자열의 시퀀스와 일치하며 각각 \* e<sub>과 일치합니다. 1</sub> *; \* e <sub>1</sub> \* _ + _는 하나 이상과 일치합니다.*e<sub>1</sub>\* _? _</span><span class="sxs-lookup"><span data-stu-id="0644f-111">are repetition operators: *e<sub>1</sub>* _\*_ matches a sequence of zero or more (possibly different) strings, each of which match *e<sub>1</sub>*; *e<sub>1</sub>* _+_ matches one or more; *e<sub>1</sub>* _?_</span></span> <span data-ttu-id="0644f-112">0 또는 1과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-112">matches zero or one.</span></span>

<span data-ttu-id="0644f-113">가장 약한 바인딩에서 가장 강한 바인딩까지 연산자 우선 순위는 먼저 교대, 다음 연결, 마지막으로 반복 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-113">The operator precedence, from weakest to strongest binding, is first alternation, then concatenation, and finally the repetition operators.</span></span> <span data-ttu-id="0644f-114">산술식에서와 같이 명시적 괄호를 사용하여 다르게 의미를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-114">Explicit parentheses can be used to force different meanings, just as in arithmetic expressions.</span></span> <span data-ttu-id="0644f-115">몇 가지 예: _ab|cd_은 _(ab)|(cd)_ 와 같습니다. _ab\*_ 는 _a(b\*)_ 와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-115">Some examples: _ab|cd_ is equivalent to _(ab)|(cd)_ ; _ab\*_ is equivalent to _a(b\*)_ .</span></span>

<span data-ttu-id="0644f-116">지금까지 설명한 구문은 대부분의 기존 Unix _egrep_ 정규식 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-116">The syntax described so far is most of the traditional Unix _egrep_ regular expression syntax.</span></span> <span data-ttu-id="0644f-117">이 하위 집합은 모든 일반 언어를 설명하는 데 충분합니다. 대략적으로하게 말하면 일반 언어는 고정된 양의 메모리만 사용하여 한 번에 텍스트를 통과하여 매칭될 수 있는 문자열 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-117">This subset suffices to describe all regular languages: loosely speaking, a regular language is a set of strings that can be matched in a single pass through the text using only a fixed amount of memory.</span></span> <span data-ttu-id="0644f-118">새로운 정규식 기능(Perl 및 이를 복사한 기능)은 수많은 새 연산자와 이스케이프 시퀀스를 추가했으며, 정규 표현식을 보다 간결하고, 때로는 암호화된 방식으로 만들기도 하지만 일반적으로 더 강력하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-118">Newer regular expression facilities (notably Perl and those that have copied it) have added many new operators and escape sequences, which make the regular expressions more concise, and sometimes more cryptic, but usually not more powerful.</span></span>

<span data-ttu-id="0644f-119">이 페이지는 RE2에서 허용하는 정규식 구문을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-119">This page lists the regular expression syntax accepted by RE2.</span></span>

<span data-ttu-id="0644f-120">또한 PCRE, PERL 및 VIM에서 허용하는 일부 구문을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-120">It also lists some syntax accepted by PCRE, PERL and VIM.</span></span>

## <a name="syntax-tables"></a><span data-ttu-id="0644f-121">구문 테이블</span><span class="sxs-lookup"><span data-stu-id="0644f-121">Syntax tables</span></span>

| <span data-ttu-id="0644f-122">단일 문자 표현의 종류</span><span class="sxs-lookup"><span data-stu-id="0644f-122">Kinds of single-character expressions</span></span> | <span data-ttu-id="0644f-123">예</span><span class="sxs-lookup"><span data-stu-id="0644f-123">Examples</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-124">모든 문자, 줄 바꿈(s=true)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-124">any character, possibly including newline (s=true)</span></span> | <span data-ttu-id="0644f-125">.</span><span class="sxs-lookup"><span data-stu-id="0644f-125">.</span></span> |
| <span data-ttu-id="0644f-126">문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-126">character class</span></span> | <span data-ttu-id="0644f-127">[xyz]</span><span class="sxs-lookup"><span data-stu-id="0644f-127">[xyz]</span></span> |
| <span data-ttu-id="0644f-128">부정 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-128">negated character class</span></span> | <span data-ttu-id="0644f-129">[^xyz]</span><span class="sxs-lookup"><span data-stu-id="0644f-129">[^xyz]</span></span> |
| <span data-ttu-id="0644f-130">Perl 문자 클래스([ 링크 ](#user-content-perl))</span><span class="sxs-lookup"><span data-stu-id="0644f-130">Perl character class ([link](#user-content-perl))</span></span> | <span data-ttu-id="0644f-131">\d</span><span class="sxs-lookup"><span data-stu-id="0644f-131">\d</span></span> |
| <span data-ttu-id="0644f-132">부정된 Perl 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-132">negated Perl character class</span></span> | <span data-ttu-id="0644f-133">\D</span><span class="sxs-lookup"><span data-stu-id="0644f-133">\D</span></span> |
| <span data-ttu-id="0644f-134">ASCII 문자 클래스([링크 ](#user-content-ascii))</span><span class="sxs-lookup"><span data-stu-id="0644f-134">ASCII character class ([link](#user-content-ascii))</span></span> | <span data-ttu-id="0644f-135">[[:alpha:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-135">[[:alpha:]]</span></span> |
| <span data-ttu-id="0644f-136">부정된 ASCII 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-136">negated ASCII character class</span></span> | <span data-ttu-id="0644f-137">[[:^alpha:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-137">[[:^alpha:]]</span></span> |
| <span data-ttu-id="0644f-138">유니코드 문자 클래스(한 글자 이름)</span><span class="sxs-lookup"><span data-stu-id="0644f-138">Unicode character class (one-letter name)</span></span> | <span data-ttu-id="0644f-139">\pN</span><span class="sxs-lookup"><span data-stu-id="0644f-139">\pN</span></span> |
| <span data-ttu-id="0644f-140">유니코드 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-140">Unicode character class</span></span> | <span data-ttu-id="0644f-141">\p{Greek}</span><span class="sxs-lookup"><span data-stu-id="0644f-141">\p{Greek}</span></span> |
| <span data-ttu-id="0644f-142">부정된 유니코드 문자 클래스(한 글자 이름)</span><span class="sxs-lookup"><span data-stu-id="0644f-142">negated Unicode character class (one-letter name)</span></span> | <span data-ttu-id="0644f-143">\PN</span><span class="sxs-lookup"><span data-stu-id="0644f-143">\PN</span></span> |
| <span data-ttu-id="0644f-144">부정된 유니코드 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-144">negated Unicode character class</span></span> | <span data-ttu-id="0644f-145">\P{Greek}</span><span class="sxs-lookup"><span data-stu-id="0644f-145">\P{Greek}</span></span> |

|&nbsp;| <span data-ttu-id="0644f-146">합성물</span><span class="sxs-lookup"><span data-stu-id="0644f-146">Composites</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-147">xy</span><span class="sxs-lookup"><span data-stu-id="0644f-147">xy</span></span> | <span data-ttu-id="0644f-148">x 다음에 y</span><span class="sxs-lookup"><span data-stu-id="0644f-148">x followed by y</span></span> |
| <span data-ttu-id="0644f-149">x\|y</span><span class="sxs-lookup"><span data-stu-id="0644f-149">x\|y</span></span> | <span data-ttu-id="0644f-150">x 또는 y(x 선호)</span><span class="sxs-lookup"><span data-stu-id="0644f-150">x or y (prefer x)</span></span> |

|&nbsp;| <span data-ttu-id="0644f-151">반복</span><span class="sxs-lookup"><span data-stu-id="0644f-151">Repetitions</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-152">x\*</span><span class="sxs-lookup"><span data-stu-id="0644f-152">x\*</span></span> | <span data-ttu-id="0644f-153">0개 이상의 x, 더 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-153">zero or more x, prefer more</span></span> |
| <span data-ttu-id="0644f-154">x+</span><span class="sxs-lookup"><span data-stu-id="0644f-154">x+</span></span> | <span data-ttu-id="0644f-155">하나 이상의 x, 더 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-155">one or more x, prefer more</span></span> |
| <span data-ttu-id="0644f-156">x?</span><span class="sxs-lookup"><span data-stu-id="0644f-156">x?</span></span> | <span data-ttu-id="0644f-157">0 개 또는 1개의 x, 1개 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-157">zero or one x, prefer one</span></span> |
| <span data-ttu-id="0644f-158">x{n,m}</span><span class="sxs-lookup"><span data-stu-id="0644f-158">x{n,m}</span></span> | <span data-ttu-id="0644f-159">n 또는 n+1 또는 ... 또는 m x, 더 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-159">n or n+1 or ... or m x, prefer more</span></span> |
| <span data-ttu-id="0644f-160">x{n,}</span><span class="sxs-lookup"><span data-stu-id="0644f-160">x{n,}</span></span> | <span data-ttu-id="0644f-161">n개 이상의 x, 더 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-161">n or more x, prefer more</span></span> |
| <span data-ttu-id="0644f-162">x{n}</span><span class="sxs-lookup"><span data-stu-id="0644f-162">x{n}</span></span> | <span data-ttu-id="0644f-163">정확히 n x</span><span class="sxs-lookup"><span data-stu-id="0644f-163">exactly n x</span></span> |
| <span data-ttu-id="0644f-164">x\*?</span><span class="sxs-lookup"><span data-stu-id="0644f-164">x\*?</span></span> | <span data-ttu-id="0644f-165">0개 이상의 x, 더 적은 것 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-165">zero or more x, prefer fewer</span></span> |
| <span data-ttu-id="0644f-166">x+?</span><span class="sxs-lookup"><span data-stu-id="0644f-166">x+?</span></span> | <span data-ttu-id="0644f-167">하나 이상의 x, 더 적은 것 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-167">one or more x, prefer fewer</span></span> |
| <span data-ttu-id="0644f-168">x??</span><span class="sxs-lookup"><span data-stu-id="0644f-168">x??</span></span> | <span data-ttu-id="0644f-169">0 또는 1 x, 0 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-169">zero or one x, prefer zero</span></span> |
| <span data-ttu-id="0644f-170">x{n,m}?</span><span class="sxs-lookup"><span data-stu-id="0644f-170">x{n,m}?</span></span> | <span data-ttu-id="0644f-171">n 또는 n+1 또는 ... 또는 m x, 더 적은 것 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-171">n or n+1 or ... or m x, prefer fewer</span></span> |
| <span data-ttu-id="0644f-172">x {n,}?</span><span class="sxs-lookup"><span data-stu-id="0644f-172">x{n,}?</span></span> | <span data-ttu-id="0644f-173">n개 이상의 x, 더 적은 것 선호</span><span class="sxs-lookup"><span data-stu-id="0644f-173">n or more x, prefer fewer</span></span> |
| <span data-ttu-id="0644f-174">x{n}?</span><span class="sxs-lookup"><span data-stu-id="0644f-174">x{n}?</span></span> | <span data-ttu-id="0644f-175">정확히 n x</span><span class="sxs-lookup"><span data-stu-id="0644f-175">exactly n x</span></span> |
| <span data-ttu-id="0644f-176">x{}</span><span class="sxs-lookup"><span data-stu-id="0644f-176">x{}</span></span> | <span data-ttu-id="0644f-177">(≡ x\*) (지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-177">(≡ x\*) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-178">x{-}</span><span class="sxs-lookup"><span data-stu-id="0644f-178">x{-}</span></span> | <span data-ttu-id="0644f-179">(≡x\*?) (지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-179">(≡ x\*?) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-180">x{-n}</span><span class="sxs-lookup"><span data-stu-id="0644f-180">x{-n}</span></span> | <span data-ttu-id="0644f-181">(≡x{n}?) (지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-181">(≡ x{n}?) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-182">x=</span><span class="sxs-lookup"><span data-stu-id="0644f-182">x=</span></span> | <span data-ttu-id="0644f-183">(≡x?) (지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-183">(≡ x?) (NOT SUPPORTED) VIM</span></span> |

<span data-ttu-id="0644f-184">구현 제한 : 계산 양식 x{n,m}, x{n,}, 및 x{n}은 최소 또는 최대 반복 횟수를 1000 이상으로 만드는 양식을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-184">Implementation restriction: The counting forms x{n,m}, x{n,}, and x{n} reject forms that create a minimum or maximum repetition count above 1000.</span></span> <span data-ttu-id="0644f-185">무제한 반복에는 이 제한이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-185">Unlimited repetitions are not subject to this restriction.</span></span>

|&nbsp;| <span data-ttu-id="0644f-186">소유 반복</span><span class="sxs-lookup"><span data-stu-id="0644f-186">Possessive repetitions</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-187">x\*+</span><span class="sxs-lookup"><span data-stu-id="0644f-187">x\*+</span></span> | <span data-ttu-id="0644f-188">0개 이상의 x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-188">zero or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-189">x++</span><span class="sxs-lookup"><span data-stu-id="0644f-189">x++</span></span> | <span data-ttu-id="0644f-190">하나 이상의 x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-190">one or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-191">x?+</span><span class="sxs-lookup"><span data-stu-id="0644f-191">x?+</span></span> | <span data-ttu-id="0644f-192">0개 또는 1개의 x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-192">zero or one x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-193">x{n,m}+</span><span class="sxs-lookup"><span data-stu-id="0644f-193">x{n,m}+</span></span> | <span data-ttu-id="0644f-194">n 또는 ... 또는 m x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-194">n or ... or m x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-195">x{n,}+</span><span class="sxs-lookup"><span data-stu-id="0644f-195">x{n,}+</span></span> | <span data-ttu-id="0644f-196">n개 이상의 x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-196">n or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-197">x{n}+</span><span class="sxs-lookup"><span data-stu-id="0644f-197">x{n}+</span></span> | <span data-ttu-id="0644f-198">정확히 n x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-198">exactly n x, possessive (NOT SUPPORTED)</span></span> |

|&nbsp;| <span data-ttu-id="0644f-199">그룹화</span><span class="sxs-lookup"><span data-stu-id="0644f-199">Grouping</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-200">(re)</span><span class="sxs-lookup"><span data-stu-id="0644f-200">(re)</span></span> | <span data-ttu-id="0644f-201">번호가 매겨진 캡처링 그룹(부분 일치)</span><span class="sxs-lookup"><span data-stu-id="0644f-201">numbered capturing group (submatch)</span></span> |
| <span data-ttu-id="0644f-202">(?P&lt;이름&gt;re)</span><span class="sxs-lookup"><span data-stu-id="0644f-202">(?P&lt;name&gt;re)</span></span> | <span data-ttu-id="0644f-203">&amp;(으)로 명명된 번호가 매겨진 캡처링 그룹(부분 일치)</span><span class="sxs-lookup"><span data-stu-id="0644f-203">named &amp; numbered capturing group (submatch)</span></span> |
| <span data-ttu-id="0644f-204">(?&lt;이름&gt;re)</span><span class="sxs-lookup"><span data-stu-id="0644f-204">(?&lt;name&gt;re)</span></span> | <span data-ttu-id="0644f-205">&amp;(으)로 명명된 번호가 매겨진 캡처링 그룹(부분 일치)(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-205">named &amp; numbered capturing group (submatch) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-206">(?&#39;이름&#39;re)</span><span class="sxs-lookup"><span data-stu-id="0644f-206">(?&#39;name&#39;re)</span></span> | <span data-ttu-id="0644f-207">&amp;(으)로 명명된 번호가 매겨진 캡처링 그룹(부분 일치)(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-207">named &amp; numbered capturing group (submatch) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-208">(?:re)</span><span class="sxs-lookup"><span data-stu-id="0644f-208">(?:re)</span></span> | <span data-ttu-id="0644f-209">비 캡처링 그룹</span><span class="sxs-lookup"><span data-stu-id="0644f-209">non-capturing group</span></span> |
| <span data-ttu-id="0644f-210">(?flags)</span><span class="sxs-lookup"><span data-stu-id="0644f-210">(?flags)</span></span> | <span data-ttu-id="0644f-211">현재 그룹 내에서 플래그를 설정합니다. 비 캡처링</span><span class="sxs-lookup"><span data-stu-id="0644f-211">set flags within current group; non-capturing</span></span> |
| <span data-ttu-id="0644f-212">(?flags:re)</span><span class="sxs-lookup"><span data-stu-id="0644f-212">(?flags:re)</span></span> | <span data-ttu-id="0644f-213">다시 수행하는 동안 플래그를 설정합니다. 비 캡처링</span><span class="sxs-lookup"><span data-stu-id="0644f-213">set flags during re; non-capturing</span></span> |
| <span data-ttu-id="0644f-214">(?#text)</span><span class="sxs-lookup"><span data-stu-id="0644f-214">(?#text)</span></span> | <span data-ttu-id="0644f-215">메모(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-215">comment (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-216">(?\|x\|y\|z)</span><span class="sxs-lookup"><span data-stu-id="0644f-216">(?\|x\|y\|z)</span></span> | <span data-ttu-id="0644f-217">분기 번호 매기기 재설정(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-217">branch numbering reset (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-218">(?&gt;re)</span><span class="sxs-lookup"><span data-stu-id="0644f-218">(?&gt;re)</span></span> | <span data-ttu-id="0644f-219">re (지원되지 않음)의 소유격 일치 결과</span><span class="sxs-lookup"><span data-stu-id="0644f-219">possessive match of re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-220">re@&gt;</span><span class="sxs-lookup"><span data-stu-id="0644f-220">re@&gt;</span></span> | <span data-ttu-id="0644f-221">re (지원되지 않음)의 소유격 일치 결과 VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-221">possessive match of re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-222">%(re)</span><span class="sxs-lookup"><span data-stu-id="0644f-222">%(re)</span></span> | <span data-ttu-id="0644f-223">비 캡처링 그룹(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-223">non-capturing group (NOT SUPPORTED) VIM</span></span> |

|&nbsp;| <span data-ttu-id="0644f-224">Flags</span><span class="sxs-lookup"><span data-stu-id="0644f-224">Flags</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-225">i</span><span class="sxs-lookup"><span data-stu-id="0644f-225">i</span></span> | <span data-ttu-id="0644f-226">대/소문자를 구분하지 않습니다(기본값 false).</span><span class="sxs-lookup"><span data-stu-id="0644f-226">case-insensitive (default false)</span></span> |
| <span data-ttu-id="0644f-227">m</span><span class="sxs-lookup"><span data-stu-id="0644f-227">m</span></span> | <span data-ttu-id="0644f-228">여러 줄 모드: ^ 및 $는 시작/끝 텍스트 외에 시작/끝 줄과 일치합니다(기본값은 false).</span><span class="sxs-lookup"><span data-stu-id="0644f-228">multi-line mode: ^ and $ match begin/end line in addition to begin/end text (default false)</span></span> |
| <span data-ttu-id="0644f-229">s</span><span class="sxs-lookup"><span data-stu-id="0644f-229">s</span></span> | <span data-ttu-id="0644f-230">허용.</span><span class="sxs-lookup"><span data-stu-id="0644f-230">let .</span></span> <span data-ttu-id="0644f-231">\n 치(기값 false)</span><span class="sxs-lookup"><span data-stu-id="0644f-231">match \n (default false)</span></span> |
| <span data-ttu-id="0644f-232">U</span><span class="sxs-lookup"><span data-stu-id="0644f-232">U</span></span> | <span data-ttu-id="0644f-233">ungreedy: x\*와 x\*?, x+ 및 x+? 등의 의미를 바꿉니다(기본값 false).</span><span class="sxs-lookup"><span data-stu-id="0644f-233">ungreedy: swap meaning of x\* and x\*?, x+ and x+?, etc (default false)</span></span> |

<span data-ttu-id="0644f-234">Flag 구문에서 xyz(설정) 또는-xyz(c제거) 는 xy z (xy 설정,z 제거)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-234">Flag syntax is xyz (set) or -xyz (clear) or xy-z (set xy, clear z).</span></span>

|&nbsp;| <span data-ttu-id="0644f-235">빈 문자열</span><span class="sxs-lookup"><span data-stu-id="0644f-235">Empty strings</span></span> |
| --- | --- |
| ^ | <span data-ttu-id="0644f-236">텍스트나 줄의 맨 앞(m = true)</span><span class="sxs-lookup"><span data-stu-id="0644f-236">at beginning of text or line (m=true)</span></span> |
| $ | <span data-ttu-id="0644f-237">행 끝(\z not \Z) 또는 회선(m = true)</span><span class="sxs-lookup"><span data-stu-id="0644f-237">at end of text (like \z not \Z) or line (m=true)</span></span> |
| <span data-ttu-id="0644f-238">\A</span><span class="sxs-lookup"><span data-stu-id="0644f-238">\A</span></span> | <span data-ttu-id="0644f-239">텍스트의 시작 부분에</span><span class="sxs-lookup"><span data-stu-id="0644f-239">at beginning of text</span></span> |
| <span data-ttu-id="0644f-240">\b</span><span class="sxs-lookup"><span data-stu-id="0644f-240">\b</span></span> | <span data-ttu-id="0644f-241">ASCII 단어 경계(1면과 \W, \A 또는 \z에 \w)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-241">at ASCII word boundary (\w on one side and \W, \A, or \z on the other)</span></span> |
| <span data-ttu-id="0644f-242">\B</span><span class="sxs-lookup"><span data-stu-id="0644f-242">\B</span></span> | <span data-ttu-id="0644f-243">ASCII 단어 경계가 아님</span><span class="sxs-lookup"><span data-stu-id="0644f-243">not at ASCII word boundary</span></span> |
| <span data-ttu-id="0644f-244">\g</span><span class="sxs-lookup"><span data-stu-id="0644f-244">\g</span></span> | <span data-ttu-id="0644f-245">검색 중인 하위 텍스트(지원되지 않음)의 시작 부분 PCRE</span><span class="sxs-lookup"><span data-stu-id="0644f-245">at beginning of subtext being searched (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="0644f-246">\G</span><span class="sxs-lookup"><span data-stu-id="0644f-246">\G</span></span> | <span data-ttu-id="0644f-247">마지막 일치 항목(지원되지 않음)의 종료 부분 PERL</span><span class="sxs-lookup"><span data-stu-id="0644f-247">at end of last match (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="0644f-248">\Z</span><span class="sxs-lookup"><span data-stu-id="0644f-248">\Z</span></span> | <span data-ttu-id="0644f-249">텍스트의 끝 또는 텍스트의 끝과 줄 바꿈 이전(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-249">at end of text, or before newline at end of text (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-250">\z</span><span class="sxs-lookup"><span data-stu-id="0644f-250">\z</span></span> | <span data-ttu-id="0644f-251">텍스트 끝</span><span class="sxs-lookup"><span data-stu-id="0644f-251">at end of text</span></span> |
| <span data-ttu-id="0644f-252">(?=re)</span><span class="sxs-lookup"><span data-stu-id="0644f-252">(?=re)</span></span> | <span data-ttu-id="0644f-253">텍스트 일치 이전(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-253">before text matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-254">%(re)</span><span class="sxs-lookup"><span data-stu-id="0644f-254">(?!re)</span></span> | <span data-ttu-id="0644f-255">텍스트 불일치 이전(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-255">before text not matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-256">(?&lt;=re)</span><span class="sxs-lookup"><span data-stu-id="0644f-256">(?&lt;=re)</span></span> | <span data-ttu-id="0644f-257">텍스트 일치(지원되지 않음) 전에</span><span class="sxs-lookup"><span data-stu-id="0644f-257">after text matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-258">(?&lt;!re)</span><span class="sxs-lookup"><span data-stu-id="0644f-258">(?&lt;!re)</span></span> | <span data-ttu-id="0644f-259">텍스트 불일치 후에(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-259">after text not matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-260">re&amp;</span><span class="sxs-lookup"><span data-stu-id="0644f-260">re&amp;</span></span> | <span data-ttu-id="0644f-261">텍스트 일치 이전(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-261">before text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-262">re@=</span><span class="sxs-lookup"><span data-stu-id="0644f-262">re@=</span></span> | <span data-ttu-id="0644f-263">텍스트 일치 이전(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-263">before text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-264">re@!</span><span class="sxs-lookup"><span data-stu-id="0644f-264">re@!</span></span> | <span data-ttu-id="0644f-265">텍스트 불일치 이전(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-265">before text not matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-266">re@&lt;=</span><span class="sxs-lookup"><span data-stu-id="0644f-266">re@&lt;=</span></span> | <span data-ttu-id="0644f-267">텍스트 일치 이전(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-267">after text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-268">re@&lt;!</span><span class="sxs-lookup"><span data-stu-id="0644f-268">re@&lt;!</span></span> | <span data-ttu-id="0644f-269">텍스트 불일치 후(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-269">after text not matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-270">\zs</span><span class="sxs-lookup"><span data-stu-id="0644f-270">\zs</span></span> | <span data-ttu-id="0644f-271">일치 시작 설정(=\K)(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-271">sets start of match (= \K) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-272">\ze</span><span class="sxs-lookup"><span data-stu-id="0644f-272">\ze</span></span> | <span data-ttu-id="0644f-273">일치 종료 설정(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-273">sets end of match (NOT SUPPORTED) VIM</span></span> |
| \%^ | <span data-ttu-id="0644f-274">파일의 시작(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-274">beginning of file (NOT SUPPORTED) VIM</span></span> |
| \%$ | <span data-ttu-id="0644f-275">파일의 시작(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-275">end of file (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-276">\%V</span><span class="sxs-lookup"><span data-stu-id="0644f-276">\%V</span></span> | <span data-ttu-id="0644f-277">화면에서(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-277">on screen (NOT SUPPORTED) VIM</span></span> |
| \%# | <span data-ttu-id="0644f-278">커서 위치(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-278">cursor position (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-279">\%&#39;m</span><span class="sxs-lookup"><span data-stu-id="0644f-279">\%&#39;m</span></span> | <span data-ttu-id="0644f-280">m 위치 표시(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-280">mark m position (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-281">\%23l</span><span class="sxs-lookup"><span data-stu-id="0644f-281">\%23l</span></span> | <span data-ttu-id="0644f-282">회선 23에서(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-282">in line 23 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-283">\%23c</span><span class="sxs-lookup"><span data-stu-id="0644f-283">\%23c</span></span> | <span data-ttu-id="0644f-284">열 23에서(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-284">in column 23 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-285">\%23v</span><span class="sxs-lookup"><span data-stu-id="0644f-285">\%23v</span></span> | <span data-ttu-id="0644f-286">가상 열 23에서(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-286">in virtual column 23 (NOT SUPPORTED) VIM</span></span> |

|&nbsp;| <span data-ttu-id="0644f-287">이스케이프 시퀀스</span><span class="sxs-lookup"><span data-stu-id="0644f-287">Escape sequences</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-288">\a</span><span class="sxs-lookup"><span data-stu-id="0644f-288">\a</span></span> | <span data-ttu-id="0644f-289">종(≡ \007)</span><span class="sxs-lookup"><span data-stu-id="0644f-289">bell (≡ \007)</span></span> |
| <span data-ttu-id="0644f-290">\f</span><span class="sxs-lookup"><span data-stu-id="0644f-290">\f</span></span> | <span data-ttu-id="0644f-291">양식 피드(≡ \014)</span><span class="sxs-lookup"><span data-stu-id="0644f-291">form feed (≡ \014)</span></span> |
| <span data-ttu-id="0644f-292">\t</span><span class="sxs-lookup"><span data-stu-id="0644f-292">\t</span></span> | <span data-ttu-id="0644f-293">수평 탭(≡ \011)</span><span class="sxs-lookup"><span data-stu-id="0644f-293">horizontal tab (≡ \011)</span></span> |
| <span data-ttu-id="0644f-294">\n</span><span class="sxs-lookup"><span data-stu-id="0644f-294">\n</span></span> | <span data-ttu-id="0644f-295">줄 바꿈(≡ \012)</span><span class="sxs-lookup"><span data-stu-id="0644f-295">newline (≡ \012)</span></span> |
| <span data-ttu-id="0644f-296">\r</span><span class="sxs-lookup"><span data-stu-id="0644f-296">\r</span></span> | <span data-ttu-id="0644f-297">캐리지 반환(≡ \015)</span><span class="sxs-lookup"><span data-stu-id="0644f-297">carriage return (≡ \015)</span></span> |
| <span data-ttu-id="0644f-298">\v</span><span class="sxs-lookup"><span data-stu-id="0644f-298">\v</span></span> | <span data-ttu-id="0644f-299">수직 탭 문자(≡ \013)</span><span class="sxs-lookup"><span data-stu-id="0644f-299">vertical tab character (≡ \013)</span></span> |
| \* | <span data-ttu-id="0644f-300">literal \*, 모든 구두점 문자인 경우 \*</span><span class="sxs-lookup"><span data-stu-id="0644f-300">literal \*, for any punctuation character \*</span></span> |
| <span data-ttu-id="0644f-301">\123</span><span class="sxs-lookup"><span data-stu-id="0644f-301">\123</span></span> | <span data-ttu-id="0644f-302">8진수 문자 코드(최대 3자리)</span><span class="sxs-lookup"><span data-stu-id="0644f-302">octal character code (up to three digits)</span></span> |
| <span data-ttu-id="0644f-303">\x7F</span><span class="sxs-lookup"><span data-stu-id="0644f-303">\x7F</span></span> | <span data-ttu-id="0644f-304">16진수 문자 코드(두 자리 수)</span><span class="sxs-lookup"><span data-stu-id="0644f-304">hex character code (exactly two digits)</span></span> |
| <span data-ttu-id="0644f-305">\x{10FFF}</span><span class="sxs-lookup"><span data-stu-id="0644f-305">\x{10FFFF}</span></span> | <span data-ttu-id="0644f-306">16진수 문자 코드</span><span class="sxs-lookup"><span data-stu-id="0644f-306">hex character code</span></span> |
| <span data-ttu-id="0644f-307">\C</span><span class="sxs-lookup"><span data-stu-id="0644f-307">\C</span></span> | <span data-ttu-id="0644f-308">UTF-8 모드에서도 단일 바이트 일치</span><span class="sxs-lookup"><span data-stu-id="0644f-308">match a single byte even in UTF-8 mode</span></span> |
| <span data-ttu-id="0644f-309">\Q...\E</span><span class="sxs-lookup"><span data-stu-id="0644f-309">\Q...\E</span></span> | <span data-ttu-id="0644f-310">리터럴 텍스트...문장 부호가 있더라도</span><span class="sxs-lookup"><span data-stu-id="0644f-310">literal text ... even if ... has punctuation</span></span> |
| <span data-ttu-id="0644f-311">\1</span><span class="sxs-lookup"><span data-stu-id="0644f-311">\1</span></span> | <span data-ttu-id="0644f-312">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-312">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-313">\b</span><span class="sxs-lookup"><span data-stu-id="0644f-313">\b</span></span> | <span data-ttu-id="0644f-314">백스페이스(지원되지 않음)(010원 사용)</span><span class="sxs-lookup"><span data-stu-id="0644f-314">backspace (NOT SUPPORTED) (use \010)</span></span> |
| <span data-ttu-id="0644f-315">\cK</span><span class="sxs-lookup"><span data-stu-id="0644f-315">\cK</span></span> | <span data-ttu-id="0644f-316">제어 문자 ^K(지원되지 않음)(\001 등 사용)</span><span class="sxs-lookup"><span data-stu-id="0644f-316">control char ^K (NOT SUPPORTED) (use \001 etc)</span></span> |
| <span data-ttu-id="0644f-317">\e</span><span class="sxs-lookup"><span data-stu-id="0644f-317">\e</span></span> | <span data-ttu-id="0644f-318">종료(지원되지 않음)(\033 사용)</span><span class="sxs-lookup"><span data-stu-id="0644f-318">escape (NOT SUPPORTED) (use \033)</span></span> |
| <span data-ttu-id="0644f-319">\g1</span><span class="sxs-lookup"><span data-stu-id="0644f-319">\g1</span></span> | <span data-ttu-id="0644f-320">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-320">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-321">\g{1}</span><span class="sxs-lookup"><span data-stu-id="0644f-321">\g{1}</span></span> | <span data-ttu-id="0644f-322">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-322">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-323">\g{+1}</span><span class="sxs-lookup"><span data-stu-id="0644f-323">\g{+1}</span></span> | <span data-ttu-id="0644f-324">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-324">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-325">\g{-1}</span><span class="sxs-lookup"><span data-stu-id="0644f-325">\g{-1}</span></span> | <span data-ttu-id="0644f-326">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-326">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-327">\g{name}</span><span class="sxs-lookup"><span data-stu-id="0644f-327">\g{name}</span></span> | <span data-ttu-id="0644f-328">명명된 백레퍼런스(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-328">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-329">\g&lt;name&gt;</span><span class="sxs-lookup"><span data-stu-id="0644f-329">\g&lt;name&gt;</span></span> | <span data-ttu-id="0644f-330">서브루틴 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-330">subroutine call (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-331">\g&#39;이름&#39;</span><span class="sxs-lookup"><span data-stu-id="0644f-331">\g&#39;name&#39;</span></span> | <span data-ttu-id="0644f-332">서브루틴 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-332">subroutine call (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-333">\k&lt;name&gt;</span><span class="sxs-lookup"><span data-stu-id="0644f-333">\k&lt;name&gt;</span></span> | <span data-ttu-id="0644f-334">명명된 백레퍼런스(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-334">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-335">\k&#39;name&#39;</span><span class="sxs-lookup"><span data-stu-id="0644f-335">\k&#39;name&#39;</span></span> | <span data-ttu-id="0644f-336">명명된 백레퍼런스(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-336">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-337">\lX</span><span class="sxs-lookup"><span data-stu-id="0644f-337">\lX</span></span> | <span data-ttu-id="0644f-338">소문자 X(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-338">lowercase X (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-339">\ux</span><span class="sxs-lookup"><span data-stu-id="0644f-339">\ux</span></span> | <span data-ttu-id="0644f-340">대문자 x(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-340">uppercase x (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-341">\L...\E</span><span class="sxs-lookup"><span data-stu-id="0644f-341">\L...\E</span></span> | <span data-ttu-id="0644f-342">소문자 텍스트...(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-342">lowercase text ... (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-343">\K</span><span class="sxs-lookup"><span data-stu-id="0644f-343">\K</span></span> | <span data-ttu-id="0644f-344">$0 시작 재설정(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-344">reset beginning of $0 (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-345">\N{name}</span><span class="sxs-lookup"><span data-stu-id="0644f-345">\N{name}</span></span> | <span data-ttu-id="0644f-346">명명된 유니코드 문자(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-346">named Unicode character (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-347">\R</span><span class="sxs-lookup"><span data-stu-id="0644f-347">\R</span></span> | <span data-ttu-id="0644f-348">회선 중단(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-348">line break (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-349">\U...\E</span><span class="sxs-lookup"><span data-stu-id="0644f-349">\U...\E</span></span> | <span data-ttu-id="0644f-350">대문자 텍스트...(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-350">upper case text ... (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-351">\X</span><span class="sxs-lookup"><span data-stu-id="0644f-351">\X</span></span> | <span data-ttu-id="0644f-352">확장 유니코드 시퀀스(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-352">extended Unicode sequence (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-353">\%d123</span><span class="sxs-lookup"><span data-stu-id="0644f-353">\%d123</span></span> | <span data-ttu-id="0644f-354">10진수 문자 123(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-354">decimal character 123 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-355">\%xFF</span><span class="sxs-lookup"><span data-stu-id="0644f-355">\%xFF</span></span> | <span data-ttu-id="0644f-356">16진수 FF(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-356">hex character FF (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-357">\%o123원</span><span class="sxs-lookup"><span data-stu-id="0644f-357">\%o123</span></span> | <span data-ttu-id="0644f-358">8진수 문자 123(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-358">octal character 123 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-359">\%u1234</span><span class="sxs-lookup"><span data-stu-id="0644f-359">\%u1234</span></span> | <span data-ttu-id="0644f-360">유니코드 문자 0x1234(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-360">Unicode character 0x1234 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-361">\%U12345678</span><span class="sxs-lookup"><span data-stu-id="0644f-361">\%U12345678</span></span> | <span data-ttu-id="0644f-362">유니코드 문자 0x12345678(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-362">Unicode character 0x12345678 (NOT SUPPORTED) VIM</span></span> |

|&nbsp;| <span data-ttu-id="0644f-363">문자 클래스 요소</span><span class="sxs-lookup"><span data-stu-id="0644f-363">Character class elements</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-364">x</span><span class="sxs-lookup"><span data-stu-id="0644f-364">x</span></span> | <span data-ttu-id="0644f-365">단일 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-365">single character</span></span> |
| <span data-ttu-id="0644f-366">A-Z</span><span class="sxs-lookup"><span data-stu-id="0644f-366">A-Z</span></span> | <span data-ttu-id="0644f-367">문자 범위(계속)</span><span class="sxs-lookup"><span data-stu-id="0644f-367">character range (inclusive)</span></span> |
| <span data-ttu-id="0644f-368">\d</span><span class="sxs-lookup"><span data-stu-id="0644f-368">\d</span></span> | <span data-ttu-id="0644f-369">펄 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-369">Perl character class</span></span> |
| <span data-ttu-id="0644f-370">[:foo:]</span><span class="sxs-lookup"><span data-stu-id="0644f-370">[:foo:]</span></span> | <span data-ttu-id="0644f-371">ASCII 문자 클래스 foo</span><span class="sxs-lookup"><span data-stu-id="0644f-371">ASCII character class foo</span></span> |
| <span data-ttu-id="0644f-372">\p{Foo}</span><span class="sxs-lookup"><span data-stu-id="0644f-372">\p{Foo}</span></span> | <span data-ttu-id="0644f-373">유니코드 문자 클래스 Foo</span><span class="sxs-lookup"><span data-stu-id="0644f-373">Unicode character class Foo</span></span> |
| <span data-ttu-id="0644f-374">\pF</span><span class="sxs-lookup"><span data-stu-id="0644f-374">\pF</span></span> | <span data-ttu-id="0644f-375">유니코드 문자 클래스 F(단일 문자 이름)</span><span class="sxs-lookup"><span data-stu-id="0644f-375">Unicode character class F (one-letter name)</span></span> |

|&nbsp;| <span data-ttu-id="0644f-376">문자 클래스 요소로 명명된 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-376">Named character classes as character class elements</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-377">[\d]</span><span class="sxs-lookup"><span data-stu-id="0644f-377">[\d]</span></span> | <span data-ttu-id="0644f-378">숫자(≡ \d)</span><span class="sxs-lookup"><span data-stu-id="0644f-378">digits (≡ \d)</span></span> |
| <span data-ttu-id="0644f-379">[^\d]</span><span class="sxs-lookup"><span data-stu-id="0644f-379">[^\d]</span></span> | <span data-ttu-id="0644f-380">숫자 아님(≡ \D)</span><span class="sxs-lookup"><span data-stu-id="0644f-380">not digits (≡ \D)</span></span> |
| <span data-ttu-id="0644f-381">[\D]</span><span class="sxs-lookup"><span data-stu-id="0644f-381">[\D]</span></span> | <span data-ttu-id="0644f-382">숫자 아님(≡ \D)</span><span class="sxs-lookup"><span data-stu-id="0644f-382">not digits (≡ \D)</span></span> |
| <span data-ttu-id="0644f-383">[^\D]</span><span class="sxs-lookup"><span data-stu-id="0644f-383">[^\D]</span></span> | <span data-ttu-id="0644f-384">숫자 없음 아님(≡ \d)</span><span class="sxs-lookup"><span data-stu-id="0644f-384">not not digits (≡ \d)</span></span> |
| <span data-ttu-id="0644f-385">[[:name:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-385">[[:name:]]</span></span> | <span data-ttu-id="0644f-386">문자 클래스 내 명명된 ASCII 클래스(문서 [:name:])</span><span class="sxs-lookup"><span data-stu-id="0644f-386">named ASCII class inside character class (≡ [:name:])</span></span> |
| <span data-ttu-id="0644f-387">[^[:name:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-387">[^[:name:]]</span></span> | <span data-ttu-id="0644f-388">부정 문자 클래스 내의 명명된 ASCII 클래스(≡ [:^name:])</span><span class="sxs-lookup"><span data-stu-id="0644f-388">named ASCII class inside negated character class (≡ [:^name:])</span></span> |
| <span data-ttu-id="0644f-389">[\p{Name}]</span><span class="sxs-lookup"><span data-stu-id="0644f-389">[\p{Name}]</span></span> | <span data-ttu-id="0644f-390">문자 클래스 내의 명명된 유니코드 속성(≡ \p{Name})</span><span class="sxs-lookup"><span data-stu-id="0644f-390">named Unicode property inside character class (≡ \p{Name})</span></span> |
| <span data-ttu-id="0644f-391">[^\p{Name}]</span><span class="sxs-lookup"><span data-stu-id="0644f-391">[^\p{Name}]</span></span> | <span data-ttu-id="0644f-392">부정된 문자 클래스 내의 명명된 유니코드 속성(≡ \P{Name})</span><span class="sxs-lookup"><span data-stu-id="0644f-392">named Unicode property inside negated character class (≡ \P{Name})</span></span> |

| <a name="user-content-perl"></a> | <span data-ttu-id="0644f-393">Perl 문자 클래스(모든 ASCII 전용)</span><span class="sxs-lookup"><span data-stu-id="0644f-393">Perl character classes (all ASCII-only)</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-394">\d</span><span class="sxs-lookup"><span data-stu-id="0644f-394">\d</span></span> | <span data-ttu-id="0644f-395">숫자(≡ [0-9])</span><span class="sxs-lookup"><span data-stu-id="0644f-395">digits (≡ [0-9])</span></span> |
| <span data-ttu-id="0644f-396">\D</span><span class="sxs-lookup"><span data-stu-id="0644f-396">\D</span></span> | <span data-ttu-id="0644f-397">숫자가 아님(≡ [^0-9])</span><span class="sxs-lookup"><span data-stu-id="0644f-397">not digits (≡ [^0-9])</span></span> |
| <span data-ttu-id="0644f-398">\s</span><span class="sxs-lookup"><span data-stu-id="0644f-398">\s</span></span> | <span data-ttu-id="0644f-399">공백(≡ [\t\n\f\r])</span><span class="sxs-lookup"><span data-stu-id="0644f-399">whitespace (≡ [\t\n\f\r])</span></span> |
| <span data-ttu-id="0644f-400">\S</span><span class="sxs-lookup"><span data-stu-id="0644f-400">\S</span></span> | <span data-ttu-id="0644f-401">공백이 아님(≡ [\t\n\f\r])</span><span class="sxs-lookup"><span data-stu-id="0644f-401">not whitespace (≡ [^\t\n\f\r])</span></span> |
| <span data-ttu-id="0644f-402">\w</span><span class="sxs-lookup"><span data-stu-id="0644f-402">\w</span></span> | <span data-ttu-id="0644f-403">단어 문자(≡ [0-9A-Za-z\_])</span><span class="sxs-lookup"><span data-stu-id="0644f-403">word characters (≡ [0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="0644f-404">\W</span><span class="sxs-lookup"><span data-stu-id="0644f-404">\W</span></span> | <span data-ttu-id="0644f-405">단어 문자가 아님(≡ [^0-9A-Za-z\_])</span><span class="sxs-lookup"><span data-stu-id="0644f-405">not word characters (≡ [^0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="0644f-406">\h</span><span class="sxs-lookup"><span data-stu-id="0644f-406">\h</span></span> | <span data-ttu-id="0644f-407">수평 공간(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-407">horizontal space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-408">\H</span><span class="sxs-lookup"><span data-stu-id="0644f-408">\H</span></span> | <span data-ttu-id="0644f-409">수평 공간이 아님(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-409">not horizontal space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-410">\v</span><span class="sxs-lookup"><span data-stu-id="0644f-410">\v</span></span> | <span data-ttu-id="0644f-411">수직 공간(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-411">vertical space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-412">\V</span><span class="sxs-lookup"><span data-stu-id="0644f-412">\V</span></span> | <span data-ttu-id="0644f-413">수직 공간이 아님(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-413">not vertical space (NOT SUPPORTED)</span></span> |

|<a name="user-content-ascii"></a>  | <span data-ttu-id="0644f-414">ASCII 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-414">ASCII character classes</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-415">[[:alnum:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-415">[[:alnum:]]</span></span> | <span data-ttu-id="0644f-416">영숫자(≡ [0-9A-Za-z])</span><span class="sxs-lookup"><span data-stu-id="0644f-416">alphanumeric (≡ [0-9A-Za-z])</span></span> |
| <span data-ttu-id="0644f-417">[[:alpha:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-417">[[:alpha:]]</span></span> | <span data-ttu-id="0644f-418">영문자(≡ [A-Za-z])</span><span class="sxs-lookup"><span data-stu-id="0644f-418">alphabetic (≡ [A-Za-z])</span></span> |
| <span data-ttu-id="0644f-419">[[:ascii:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-419">[[:ascii:]]</span></span> | <span data-ttu-id="0644f-420">ASCII (≡ [\x00-\x7F])</span><span class="sxs-lookup"><span data-stu-id="0644f-420">ASCII (≡ [\x00-\x7F])</span></span> |
| <span data-ttu-id="0644f-421">[[:blank:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-421">[[:blank:]]</span></span> | <span data-ttu-id="0644f-422">공백(≡ [\t])</span><span class="sxs-lookup"><span data-stu-id="0644f-422">blank (≡ [\t])</span></span> |
| <span data-ttu-id="0644f-423">[[:cntrl:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-423">[[:cntrl:]]</span></span> | <span data-ttu-id="0644f-424">컨트롤(≡ [\x00-\x1F\x7F])</span><span class="sxs-lookup"><span data-stu-id="0644f-424">control (≡ [\x00-\x1F\x7F])</span></span> |
| <span data-ttu-id="0644f-425">[[:digit:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-425">[[:digit:]]</span></span> | <span data-ttu-id="0644f-426">숫자(≡ [0-9])</span><span class="sxs-lookup"><span data-stu-id="0644f-426">digits (≡ [0-9])</span></span> |
| <span data-ttu-id="0644f-427">[[:graph:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-427">[[:graph:]]</span></span> | <span data-ttu-id="0644f-428">그래픽(≡ `[!-~]` ≡ `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`)</span><span class="sxs-lookup"><span data-stu-id="0644f-428">graphical (≡ `[!-~]` ≡ `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`)</span></span> |
| <span data-ttu-id="0644f-429">[[:lower:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-429">[[:lower:]]</span></span> | <span data-ttu-id="0644f-430">소문자(≡ [a-z])</span><span class="sxs-lookup"><span data-stu-id="0644f-430">lower case (≡ [a-z])</span></span> |
| <span data-ttu-id="0644f-431">[[:print:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-431">[[:print:]]</span></span> | <span data-ttu-id="0644f-432">인쇄 가능(≡ [-~] ≡ [[:graph:]])</span><span class="sxs-lookup"><span data-stu-id="0644f-432">printable (≡ [-~] ≡ [[:graph:]])</span></span> |
| <span data-ttu-id="0644f-433">[[:punct:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-433">[[:punct:]]</span></span> | <span data-ttu-id="0644f-434">구두점(≡ [!-/:-@[-\`{-~])</span><span class="sxs-lookup"><span data-stu-id="0644f-434">punctuation (≡ [!-/:-@[-\`{-~])</span></span> |
| <span data-ttu-id="0644f-435">[[:space:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-435">[[:space:]]</span></span> | <span data-ttu-id="0644f-436">흰 공백(≡ [\t\n\v\f\r])</span><span class="sxs-lookup"><span data-stu-id="0644f-436">whitespace (≡ [\t\n\v\f\r])</span></span> |
| <span data-ttu-id="0644f-437">[[:upper:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-437">[[:upper:]]</span></span> | <span data-ttu-id="0644f-438">대문자(≡ [A-Z])</span><span class="sxs-lookup"><span data-stu-id="0644f-438">upper case (≡ [A-Z])</span></span> |
| <span data-ttu-id="0644f-439">[[:word:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-439">[[:word:]]</span></span> | <span data-ttu-id="0644f-440">단어 문자(≡ [0-9A-Za-z\_])</span><span class="sxs-lookup"><span data-stu-id="0644f-440">word characters (≡ [0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="0644f-441">[[:xdigit:]]</span><span class="sxs-lookup"><span data-stu-id="0644f-441">[[:xdigit:]]</span></span> | <span data-ttu-id="0644f-442">16진수(≡ [0-9A-Fa-f])</span><span class="sxs-lookup"><span data-stu-id="0644f-442">hex digit (≡ [0-9A-Fa-f])</span></span> |

|&nbsp;| <span data-ttu-id="0644f-443">유니코드 문자 클래스 이름--일반 카테고리</span><span class="sxs-lookup"><span data-stu-id="0644f-443">Unicode character class names--general category</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-444">C</span><span class="sxs-lookup"><span data-stu-id="0644f-444">C</span></span> | <span data-ttu-id="0644f-445">기타</span><span class="sxs-lookup"><span data-stu-id="0644f-445">other</span></span> |
| <span data-ttu-id="0644f-446">참조</span><span class="sxs-lookup"><span data-stu-id="0644f-446">Cc</span></span> | <span data-ttu-id="0644f-447">control</span><span class="sxs-lookup"><span data-stu-id="0644f-447">control</span></span> |
| <span data-ttu-id="0644f-448">Cf</span><span class="sxs-lookup"><span data-stu-id="0644f-448">Cf</span></span> | <span data-ttu-id="0644f-449">형식</span><span class="sxs-lookup"><span data-stu-id="0644f-449">format</span></span> |
| <span data-ttu-id="0644f-450">Cn</span><span class="sxs-lookup"><span data-stu-id="0644f-450">Cn</span></span> | <span data-ttu-id="0644f-451">할당되지 않은 코드 포인트(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-451">unassigned code points (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-452">Co</span><span class="sxs-lookup"><span data-stu-id="0644f-452">Co</span></span> | <span data-ttu-id="0644f-453">비공개 사용</span><span class="sxs-lookup"><span data-stu-id="0644f-453">private use</span></span> |
| <span data-ttu-id="0644f-454">Cs</span><span class="sxs-lookup"><span data-stu-id="0644f-454">Cs</span></span> | <span data-ttu-id="0644f-455">서로게이트</span><span class="sxs-lookup"><span data-stu-id="0644f-455">surrogate</span></span> |
| <span data-ttu-id="0644f-456">L</span><span class="sxs-lookup"><span data-stu-id="0644f-456">L</span></span> | <span data-ttu-id="0644f-457">글자</span><span class="sxs-lookup"><span data-stu-id="0644f-457">letter</span></span> |
| <span data-ttu-id="0644f-458">LC</span><span class="sxs-lookup"><span data-stu-id="0644f-458">LC</span></span> | <span data-ttu-id="0644f-459">대/소문자(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-459">cased letter (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-460">L&amp;</span><span class="sxs-lookup"><span data-stu-id="0644f-460">L&amp;</span></span> | <span data-ttu-id="0644f-461">대/소문자(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-461">cased letter (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-462">Ll</span><span class="sxs-lookup"><span data-stu-id="0644f-462">Ll</span></span> | <span data-ttu-id="0644f-463">소문자</span><span class="sxs-lookup"><span data-stu-id="0644f-463">lowercase letter</span></span> |
| <span data-ttu-id="0644f-464">Lm</span><span class="sxs-lookup"><span data-stu-id="0644f-464">Lm</span></span> | <span data-ttu-id="0644f-465">수식어</span><span class="sxs-lookup"><span data-stu-id="0644f-465">modifier letter</span></span> |
| <span data-ttu-id="0644f-466">Lo</span><span class="sxs-lookup"><span data-stu-id="0644f-466">Lo</span></span> | <span data-ttu-id="0644f-467">다른 편지</span><span class="sxs-lookup"><span data-stu-id="0644f-467">other letter</span></span> |
| <span data-ttu-id="0644f-468">LT</span><span class="sxs-lookup"><span data-stu-id="0644f-468">Lt</span></span> | <span data-ttu-id="0644f-469">제목 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-469">titlecase letter</span></span> |
| <span data-ttu-id="0644f-470">Lu</span><span class="sxs-lookup"><span data-stu-id="0644f-470">Lu</span></span> | <span data-ttu-id="0644f-471">대문자</span><span class="sxs-lookup"><span data-stu-id="0644f-471">uppercase letter</span></span> |
| <span data-ttu-id="0644f-472">M</span><span class="sxs-lookup"><span data-stu-id="0644f-472">M</span></span> | <span data-ttu-id="0644f-473">표시</span><span class="sxs-lookup"><span data-stu-id="0644f-473">mark</span></span> |
| <span data-ttu-id="0644f-474">Mc</span><span class="sxs-lookup"><span data-stu-id="0644f-474">Mc</span></span> | <span data-ttu-id="0644f-475">간격 표시</span><span class="sxs-lookup"><span data-stu-id="0644f-475">spacing mark</span></span> |
| <span data-ttu-id="0644f-476">Me</span><span class="sxs-lookup"><span data-stu-id="0644f-476">Me</span></span> | <span data-ttu-id="0644f-477">묶기 표시</span><span class="sxs-lookup"><span data-stu-id="0644f-477">enclosing mark</span></span> |
| <span data-ttu-id="0644f-478">Mn</span><span class="sxs-lookup"><span data-stu-id="0644f-478">Mn</span></span> | <span data-ttu-id="0644f-479">간격 없음 표시</span><span class="sxs-lookup"><span data-stu-id="0644f-479">non-spacing mark</span></span> |
| <span data-ttu-id="0644f-480">N</span><span class="sxs-lookup"><span data-stu-id="0644f-480">N</span></span> | <span data-ttu-id="0644f-481">숫자</span><span class="sxs-lookup"><span data-stu-id="0644f-481">number</span></span> |
| <span data-ttu-id="0644f-482">Nd</span><span class="sxs-lookup"><span data-stu-id="0644f-482">Nd</span></span> | <span data-ttu-id="0644f-483">십진수</span><span class="sxs-lookup"><span data-stu-id="0644f-483">decimal number</span></span> |
| <span data-ttu-id="0644f-484">Nl</span><span class="sxs-lookup"><span data-stu-id="0644f-484">Nl</span></span> | <span data-ttu-id="0644f-485">문자 번호</span><span class="sxs-lookup"><span data-stu-id="0644f-485">letter number</span></span> |
| <span data-ttu-id="0644f-486">아니오</span><span class="sxs-lookup"><span data-stu-id="0644f-486">No</span></span> | <span data-ttu-id="0644f-487">그 외 숫자</span><span class="sxs-lookup"><span data-stu-id="0644f-487">other number</span></span> |
| <span data-ttu-id="0644f-488">P</span><span class="sxs-lookup"><span data-stu-id="0644f-488">P</span></span> | <span data-ttu-id="0644f-489">구두점</span><span class="sxs-lookup"><span data-stu-id="0644f-489">punctuation</span></span> |
| <span data-ttu-id="0644f-490">Pc</span><span class="sxs-lookup"><span data-stu-id="0644f-490">Pc</span></span> | <span data-ttu-id="0644f-491">커넥터 구두점</span><span class="sxs-lookup"><span data-stu-id="0644f-491">connector punctuation</span></span> |
| <span data-ttu-id="0644f-492">Pd</span><span class="sxs-lookup"><span data-stu-id="0644f-492">Pd</span></span> | <span data-ttu-id="0644f-493">대시 구두점</span><span class="sxs-lookup"><span data-stu-id="0644f-493">dash punctuation</span></span> |
| <span data-ttu-id="0644f-494">Pe</span><span class="sxs-lookup"><span data-stu-id="0644f-494">Pe</span></span> | <span data-ttu-id="0644f-495">구두점 닫기</span><span class="sxs-lookup"><span data-stu-id="0644f-495">close punctuation</span></span> |
| <span data-ttu-id="0644f-496">Pf</span><span class="sxs-lookup"><span data-stu-id="0644f-496">Pf</span></span> | <span data-ttu-id="0644f-497">최종 구두점</span><span class="sxs-lookup"><span data-stu-id="0644f-497">final punctuation</span></span> |
| <span data-ttu-id="0644f-498">Pi</span><span class="sxs-lookup"><span data-stu-id="0644f-498">Pi</span></span> | <span data-ttu-id="0644f-499">초기 구두점</span><span class="sxs-lookup"><span data-stu-id="0644f-499">initial punctuation</span></span> |
| <span data-ttu-id="0644f-500">Po</span><span class="sxs-lookup"><span data-stu-id="0644f-500">Po</span></span> | <span data-ttu-id="0644f-501">기타 구두점</span><span class="sxs-lookup"><span data-stu-id="0644f-501">other punctuation</span></span> |
| <span data-ttu-id="0644f-502">Ps</span><span class="sxs-lookup"><span data-stu-id="0644f-502">Ps</span></span> | <span data-ttu-id="0644f-503">구두점 열기</span><span class="sxs-lookup"><span data-stu-id="0644f-503">open punctuation</span></span> |
| <span data-ttu-id="0644f-504">S</span><span class="sxs-lookup"><span data-stu-id="0644f-504">S</span></span> | <span data-ttu-id="0644f-505">symbol</span><span class="sxs-lookup"><span data-stu-id="0644f-505">symbol</span></span> |
| <span data-ttu-id="0644f-506">Sc</span><span class="sxs-lookup"><span data-stu-id="0644f-506">Sc</span></span> | <span data-ttu-id="0644f-507">통화 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-507">currency symbol</span></span> |
| <span data-ttu-id="0644f-508">Sk</span><span class="sxs-lookup"><span data-stu-id="0644f-508">Sk</span></span> | <span data-ttu-id="0644f-509">수식어 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-509">modifier symbol</span></span> |
| <span data-ttu-id="0644f-510">Sm</span><span class="sxs-lookup"><span data-stu-id="0644f-510">Sm</span></span> | <span data-ttu-id="0644f-511">수학 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-511">math symbol</span></span> |
| <span data-ttu-id="0644f-512">So</span><span class="sxs-lookup"><span data-stu-id="0644f-512">So</span></span> | <span data-ttu-id="0644f-513">기타 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-513">other symbol</span></span> |
| <span data-ttu-id="0644f-514">Z</span><span class="sxs-lookup"><span data-stu-id="0644f-514">Z</span></span> | <span data-ttu-id="0644f-515">구분 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-515">separator</span></span> |
| <span data-ttu-id="0644f-516">Zl</span><span class="sxs-lookup"><span data-stu-id="0644f-516">Zl</span></span> | <span data-ttu-id="0644f-517">선 구분 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-517">line separator</span></span> |
| <span data-ttu-id="0644f-518">Zp</span><span class="sxs-lookup"><span data-stu-id="0644f-518">Zp</span></span> | <span data-ttu-id="0644f-519">단락 구분 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-519">paragraph separator</span></span> |
| <span data-ttu-id="0644f-520">Zs</span><span class="sxs-lookup"><span data-stu-id="0644f-520">Zs</span></span> | <span data-ttu-id="0644f-521">공간 구분 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-521">space separator</span></span> |

| <span data-ttu-id="0644f-522">유니코드 문자 클래스 이름--스크립트</span><span class="sxs-lookup"><span data-stu-id="0644f-522">Unicode character class names--scripts</span></span> |
| --- |
| <span data-ttu-id="0644f-523">아들람 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-523">Adlam</span></span> |
| <span data-ttu-id="0644f-524">아홈 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-524">Ahom</span></span> |
| <span data-ttu-id="0644f-525">아나톨리안\_상형문자</span><span class="sxs-lookup"><span data-stu-id="0644f-525">Anatolian\_Hieroglyphs</span></span> |
| <span data-ttu-id="0644f-526">아랍어</span><span class="sxs-lookup"><span data-stu-id="0644f-526">Arabic</span></span> |
| <span data-ttu-id="0644f-527">아르메니아어</span><span class="sxs-lookup"><span data-stu-id="0644f-527">Armenian</span></span> |
| <span data-ttu-id="0644f-528">아베스타 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-528">Avestan</span></span> |
| <span data-ttu-id="0644f-529">발리어</span><span class="sxs-lookup"><span data-stu-id="0644f-529">Balinese</span></span> |
| <span data-ttu-id="0644f-530">바뭄 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-530">Bamum</span></span> |
| <span data-ttu-id="0644f-531">Bassa\_Vah</span><span class="sxs-lookup"><span data-stu-id="0644f-531">Bassa\_Vah</span></span> |
| <span data-ttu-id="0644f-532">바타크 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-532">Batak</span></span> |
| <span data-ttu-id="0644f-533">벵골어</span><span class="sxs-lookup"><span data-stu-id="0644f-533">Bengali</span></span> |
| <span data-ttu-id="0644f-534">바이크슈키 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-534">Bhaiksuki</span></span> |
| <span data-ttu-id="0644f-535">보포모포 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-535">Bopomofo</span></span> |
| <span data-ttu-id="0644f-536">브라미 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-536">Brahmi</span></span> |
| <span data-ttu-id="0644f-537">점자</span><span class="sxs-lookup"><span data-stu-id="0644f-537">Braille</span></span> |
| <span data-ttu-id="0644f-538">부기어</span><span class="sxs-lookup"><span data-stu-id="0644f-538">Buginese</span></span> |
| <span data-ttu-id="0644f-539">부히드어</span><span class="sxs-lookup"><span data-stu-id="0644f-539">Buhid</span></span> |
| <span data-ttu-id="0644f-540">캐나다인\_원주민</span><span class="sxs-lookup"><span data-stu-id="0644f-540">Canadian\_Aboriginal</span></span> |
| <span data-ttu-id="0644f-541">카리안</span><span class="sxs-lookup"><span data-stu-id="0644f-541">Carian</span></span> |
| <span data-ttu-id="0644f-542">백인\_알바니아어</span><span class="sxs-lookup"><span data-stu-id="0644f-542">Caucasian\_Albanian</span></span> |
| <span data-ttu-id="0644f-543">차크마 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-543">Chakma</span></span> |
| <span data-ttu-id="0644f-544">Cham</span><span class="sxs-lookup"><span data-stu-id="0644f-544">Cham</span></span> |
| <span data-ttu-id="0644f-545">체로키어</span><span class="sxs-lookup"><span data-stu-id="0644f-545">Cherokee</span></span> |
| <span data-ttu-id="0644f-546">초라스미안</span><span class="sxs-lookup"><span data-stu-id="0644f-546">Chorasmian</span></span> |
| <span data-ttu-id="0644f-547">일반</span><span class="sxs-lookup"><span data-stu-id="0644f-547">Common</span></span> |
| <span data-ttu-id="0644f-548">콥트어</span><span class="sxs-lookup"><span data-stu-id="0644f-548">Coptic</span></span> |
| <span data-ttu-id="0644f-549">쿠네오페어</span><span class="sxs-lookup"><span data-stu-id="0644f-549">Cuneiform</span></span> |
| <span data-ttu-id="0644f-550">키프로스어</span><span class="sxs-lookup"><span data-stu-id="0644f-550">Cypriot</span></span> |
| <span data-ttu-id="0644f-551">키릴 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-551">Cyrillic</span></span> |
| <span data-ttu-id="0644f-552">데저렛 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-552">Deseret</span></span> |
| <span data-ttu-id="0644f-553">데바나가리어</span><span class="sxs-lookup"><span data-stu-id="0644f-553">Devanagari</span></span> |
| <span data-ttu-id="0644f-554">디브스\_아쿠루</span><span class="sxs-lookup"><span data-stu-id="0644f-554">Dives\_Akuru</span></span> |
| <span data-ttu-id="0644f-555">도그라 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-555">Dogra</span></span> |
| <span data-ttu-id="0644f-556">듀플로이안 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-556">Duployan</span></span> |
| <span data-ttu-id="0644f-557">이집트\_상형문자</span><span class="sxs-lookup"><span data-stu-id="0644f-557">Egyptian\_Hieroglyphs</span></span> |
| <span data-ttu-id="0644f-558">엘바산 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-558">Elbasan</span></span> |
| <span data-ttu-id="0644f-559">엘리마어</span><span class="sxs-lookup"><span data-stu-id="0644f-559">Elymaic</span></span> |
| <span data-ttu-id="0644f-560">에티오피아어</span><span class="sxs-lookup"><span data-stu-id="0644f-560">Ethiopic</span></span> |
| <span data-ttu-id="0644f-561">그루지야어</span><span class="sxs-lookup"><span data-stu-id="0644f-561">Georgian</span></span> |
| <span data-ttu-id="0644f-562">글라골어</span><span class="sxs-lookup"><span data-stu-id="0644f-562">Glagolitic</span></span> |
| <span data-ttu-id="0644f-563">고딕어</span><span class="sxs-lookup"><span data-stu-id="0644f-563">Gothic</span></span> |
| <span data-ttu-id="0644f-564">그란타 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-564">Grantha</span></span> |
| <span data-ttu-id="0644f-565">그리스어</span><span class="sxs-lookup"><span data-stu-id="0644f-565">Greek</span></span> |
| <span data-ttu-id="0644f-566">구자라트어</span><span class="sxs-lookup"><span data-stu-id="0644f-566">Gujarati</span></span> |
| <span data-ttu-id="0644f-567">Gunjala\_Gondi</span><span class="sxs-lookup"><span data-stu-id="0644f-567">Gunjala\_Gondi</span></span> |
| <span data-ttu-id="0644f-568">굴묵키어</span><span class="sxs-lookup"><span data-stu-id="0644f-568">Gurmukhi</span></span> |
| <span data-ttu-id="0644f-569">간체</span><span class="sxs-lookup"><span data-stu-id="0644f-569">Han</span></span> |
| <span data-ttu-id="0644f-570">한글</span><span class="sxs-lookup"><span data-stu-id="0644f-570">Hangul</span></span> |
| <span data-ttu-id="0644f-571">하니피\_로힝야</span><span class="sxs-lookup"><span data-stu-id="0644f-571">Hanifi\_Rohingya</span></span> |
| <span data-ttu-id="0644f-572">하누누어</span><span class="sxs-lookup"><span data-stu-id="0644f-572">Hanunoo</span></span> |
| <span data-ttu-id="0644f-573">해트란 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-573">Hatran</span></span> |
| <span data-ttu-id="0644f-574">히브리어</span><span class="sxs-lookup"><span data-stu-id="0644f-574">Hebrew</span></span> |
| <span data-ttu-id="0644f-575">히라가나</span><span class="sxs-lookup"><span data-stu-id="0644f-575">Hiragana</span></span> |
| <span data-ttu-id="0644f-576">임페리얼\_아람어</span><span class="sxs-lookup"><span data-stu-id="0644f-576">Imperial\_Aramaic</span></span> |
| <span data-ttu-id="0644f-577">상속됨</span><span class="sxs-lookup"><span data-stu-id="0644f-577">Inherited</span></span> |
| <span data-ttu-id="0644f-578">비문\_팔라비</span><span class="sxs-lookup"><span data-stu-id="0644f-578">Inscriptional\_Pahlavi</span></span> |
| <span data-ttu-id="0644f-579">비문\_파르티아누스</span><span class="sxs-lookup"><span data-stu-id="0644f-579">Inscriptional\_Parthian</span></span> |
| <span data-ttu-id="0644f-580">자바어</span><span class="sxs-lookup"><span data-stu-id="0644f-580">Javanese</span></span> |
| <span data-ttu-id="0644f-581">카이티 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-581">Kaithi</span></span> |
| <span data-ttu-id="0644f-582">칸나다어</span><span class="sxs-lookup"><span data-stu-id="0644f-582">Kannada</span></span> |
| <span data-ttu-id="0644f-583">가타카나</span><span class="sxs-lookup"><span data-stu-id="0644f-583">Katakana</span></span> |
| <span data-ttu-id="0644f-584">카야\_리</span><span class="sxs-lookup"><span data-stu-id="0644f-584">Kayah\_Li</span></span> |
| <span data-ttu-id="0644f-585">하로쉬티</span><span class="sxs-lookup"><span data-stu-id="0644f-585">Kharoshthi</span></span> |
| <span data-ttu-id="0644f-586">키탄\_스몰\_스크립트</span><span class="sxs-lookup"><span data-stu-id="0644f-586">Khitan\_Small\_Script</span></span> |
| <span data-ttu-id="0644f-587">크메르어</span><span class="sxs-lookup"><span data-stu-id="0644f-587">Khmer</span></span> |
| <span data-ttu-id="0644f-588">코지키</span><span class="sxs-lookup"><span data-stu-id="0644f-588">Khojki</span></span> |
| <span data-ttu-id="0644f-589">후다와디</span><span class="sxs-lookup"><span data-stu-id="0644f-589">Khudawadi</span></span> |
| <span data-ttu-id="0644f-590">라오스어</span><span class="sxs-lookup"><span data-stu-id="0644f-590">Lao</span></span> |
| <span data-ttu-id="0644f-591">라틴어</span><span class="sxs-lookup"><span data-stu-id="0644f-591">Latin</span></span> |
| <span data-ttu-id="0644f-592">렙차어</span><span class="sxs-lookup"><span data-stu-id="0644f-592">Lepcha</span></span> |
| <span data-ttu-id="0644f-593">림부어</span><span class="sxs-lookup"><span data-stu-id="0644f-593">Limbu</span></span> |
| <span data-ttu-id="0644f-594">선형\_A</span><span class="sxs-lookup"><span data-stu-id="0644f-594">Linear\_A</span></span> |
| <span data-ttu-id="0644f-595">선형\_B</span><span class="sxs-lookup"><span data-stu-id="0644f-595">Linear\_B</span></span> |
| <span data-ttu-id="0644f-596">리쑤 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-596">Lisu</span></span> |
| <span data-ttu-id="0644f-597">리키아 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-597">Lycian</span></span> |
| <span data-ttu-id="0644f-598">리디아 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-598">Lydian</span></span> |
| <span data-ttu-id="0644f-599">마하자니 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-599">Mahajani</span></span> |
| <span data-ttu-id="0644f-600">마카사르 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-600">Makasar</span></span> |
| <span data-ttu-id="0644f-601">말라얄람어</span><span class="sxs-lookup"><span data-stu-id="0644f-601">Malayalam</span></span> |
| <span data-ttu-id="0644f-602">만다이아 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-602">Mandaic</span></span> |
| <span data-ttu-id="0644f-603">마니 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-603">Manichaean</span></span> |
| <span data-ttu-id="0644f-604">마르첸 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-604">Marchen</span></span> |
| <span data-ttu-id="0644f-605">Masaram\_Gondi</span><span class="sxs-lookup"><span data-stu-id="0644f-605">Masaram\_Gondi</span></span> |
| <span data-ttu-id="0644f-606">Medefaidrin</span><span class="sxs-lookup"><span data-stu-id="0644f-606">Medefaidrin</span></span> |
| <span data-ttu-id="0644f-607">Meetei\_Mayek</span><span class="sxs-lookup"><span data-stu-id="0644f-607">Meetei\_Mayek</span></span> |
| <span data-ttu-id="0644f-608">Mende\_Kikakui</span><span class="sxs-lookup"><span data-stu-id="0644f-608">Mende\_Kikakui</span></span> |
| <span data-ttu-id="0644f-609">메로이틱\_커시브</span><span class="sxs-lookup"><span data-stu-id="0644f-609">Meroitic\_Cursive</span></span> |
| <span data-ttu-id="0644f-610">메로이틱\_상형문자</span><span class="sxs-lookup"><span data-stu-id="0644f-610">Meroitic\_Hieroglyphs</span></span> |
| <span data-ttu-id="0644f-611">먀오 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-611">Miao</span></span> |
| <span data-ttu-id="0644f-612">모디</span><span class="sxs-lookup"><span data-stu-id="0644f-612">Modi</span></span> |
| <span data-ttu-id="0644f-613">몽골어</span><span class="sxs-lookup"><span data-stu-id="0644f-613">Mongolian</span></span> |
| <span data-ttu-id="0644f-614">Mro</span><span class="sxs-lookup"><span data-stu-id="0644f-614">Mro</span></span> |
| <span data-ttu-id="0644f-615">Multani</span><span class="sxs-lookup"><span data-stu-id="0644f-615">Multani</span></span> |
| <span data-ttu-id="0644f-616">미얀마</span><span class="sxs-lookup"><span data-stu-id="0644f-616">Myanmar</span></span> |
| <span data-ttu-id="0644f-617">나바테안 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-617">Nabataean</span></span> |
| <span data-ttu-id="0644f-618">난디 나가리 기호</span><span class="sxs-lookup"><span data-stu-id="0644f-618">Nandinagari</span></span> |
| <span data-ttu-id="0644f-619">New\_Tai\_Lue</span><span class="sxs-lookup"><span data-stu-id="0644f-619">New\_Tai\_Lue</span></span> |
| <span data-ttu-id="0644f-620">뉴아</span><span class="sxs-lookup"><span data-stu-id="0644f-620">Newa</span></span> |
| <span data-ttu-id="0644f-621">은코어</span><span class="sxs-lookup"><span data-stu-id="0644f-621">Nko</span></span> |
| <span data-ttu-id="0644f-622">Nushu</span><span class="sxs-lookup"><span data-stu-id="0644f-622">Nushu</span></span> |
| <span data-ttu-id="0644f-623">Nyiakeng\_Puachue\_Hmong</span><span class="sxs-lookup"><span data-stu-id="0644f-623">Nyiakeng\_Puachue\_Hmong</span></span> |
| <span data-ttu-id="0644f-624">Ogham</span><span class="sxs-lookup"><span data-stu-id="0644f-624">Ogham</span></span> |
| <span data-ttu-id="0644f-625">Ol\_Chiki</span><span class="sxs-lookup"><span data-stu-id="0644f-625">Ol\_Chiki</span></span> |
| <span data-ttu-id="0644f-626">고대\_헝가리어</span><span class="sxs-lookup"><span data-stu-id="0644f-626">Old\_Hungarian</span></span> |
| <span data-ttu-id="0644f-627">고대\_이탈리아어</span><span class="sxs-lookup"><span data-stu-id="0644f-627">Old\_Italic</span></span> |
| <span data-ttu-id="0644f-628">고대\_북\_아랍어</span><span class="sxs-lookup"><span data-stu-id="0644f-628">Old\_North\_Arabian</span></span> |
| <span data-ttu-id="0644f-629">고대\_페름 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-629">Old\_Permic</span></span> |
| <span data-ttu-id="0644f-630">고대\_페르시아 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-630">Old\_Persian</span></span> |
| <span data-ttu-id="0644f-631">고대\_Sogdian</span><span class="sxs-lookup"><span data-stu-id="0644f-631">Old\_Sogdian</span></span> |
| <span data-ttu-id="0644f-632">고대\_남\_아랍어</span><span class="sxs-lookup"><span data-stu-id="0644f-632">Old\_South\_Arabian</span></span> |
| <span data-ttu-id="0644f-633">고대\_터키어</span><span class="sxs-lookup"><span data-stu-id="0644f-633">Old\_Turkic</span></span> |
| <span data-ttu-id="0644f-634">오리야어</span><span class="sxs-lookup"><span data-stu-id="0644f-634">Oriya</span></span> |
| <span data-ttu-id="0644f-635">오사게</span><span class="sxs-lookup"><span data-stu-id="0644f-635">Osage</span></span> |
| <span data-ttu-id="0644f-636">오스만야</span><span class="sxs-lookup"><span data-stu-id="0644f-636">Osmanya</span></span> |
| <span data-ttu-id="0644f-637">Pahawh\_Hmong</span><span class="sxs-lookup"><span data-stu-id="0644f-637">Pahawh\_Hmong</span></span> |
| <span data-ttu-id="0644f-638">Palmyrene</span><span class="sxs-lookup"><span data-stu-id="0644f-638">Palmyrene</span></span> |
| <span data-ttu-id="0644f-639">Pau\_Cin\_Hau</span><span class="sxs-lookup"><span data-stu-id="0644f-639">Pau\_Cin\_Hau</span></span> |
| <span data-ttu-id="0644f-640">Phags\_Pa</span><span class="sxs-lookup"><span data-stu-id="0644f-640">Phags\_Pa</span></span> |
| <span data-ttu-id="0644f-641">페니키아 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-641">Phoenician</span></span> |
| <span data-ttu-id="0644f-642">Psalter\_Pahlavi</span><span class="sxs-lookup"><span data-stu-id="0644f-642">Psalter\_Pahlavi</span></span> |
| <span data-ttu-id="0644f-643">레장 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-643">Rejang</span></span> |
| <span data-ttu-id="0644f-644">룬어</span><span class="sxs-lookup"><span data-stu-id="0644f-644">Runic</span></span> |
| <span data-ttu-id="0644f-645">사마리아 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-645">Samaritan</span></span> |
| <span data-ttu-id="0644f-646">사우라슈트라</span><span class="sxs-lookup"><span data-stu-id="0644f-646">Saurashtra</span></span> |
| <span data-ttu-id="0644f-647">Sharada</span><span class="sxs-lookup"><span data-stu-id="0644f-647">Sharada</span></span> |
| <span data-ttu-id="0644f-648">샤우 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-648">Shavian</span></span> |
| <span data-ttu-id="0644f-649">Siddham</span><span class="sxs-lookup"><span data-stu-id="0644f-649">Siddham</span></span> |
| <span data-ttu-id="0644f-650">수화 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-650">SignWriting</span></span> |
| <span data-ttu-id="0644f-651">싱할라어</span><span class="sxs-lookup"><span data-stu-id="0644f-651">Sinhala</span></span> |
| <span data-ttu-id="0644f-652">Sogdian</span><span class="sxs-lookup"><span data-stu-id="0644f-652">Sogdian</span></span> |
| <span data-ttu-id="0644f-653">Sora\_Sompeng</span><span class="sxs-lookup"><span data-stu-id="0644f-653">Sora\_Sompeng</span></span> |
| <span data-ttu-id="0644f-654">Soyombo</span><span class="sxs-lookup"><span data-stu-id="0644f-654">Soyombo</span></span> |
| <span data-ttu-id="0644f-655">순다어</span><span class="sxs-lookup"><span data-stu-id="0644f-655">Sundanese</span></span> |
| <span data-ttu-id="0644f-656">Syloti\_Nagri</span><span class="sxs-lookup"><span data-stu-id="0644f-656">Syloti\_Nagri</span></span> |
| <span data-ttu-id="0644f-657">시리아어</span><span class="sxs-lookup"><span data-stu-id="0644f-657">Syriac</span></span> |
| <span data-ttu-id="0644f-658">타갈로그어</span><span class="sxs-lookup"><span data-stu-id="0644f-658">Tagalog</span></span> |
| <span data-ttu-id="0644f-659">타그반와어</span><span class="sxs-lookup"><span data-stu-id="0644f-659">Tagbanwa</span></span> |
| <span data-ttu-id="0644f-660">Tai\_Le</span><span class="sxs-lookup"><span data-stu-id="0644f-660">Tai\_Le</span></span> |
| <span data-ttu-id="0644f-661">Tai\_Tham</span><span class="sxs-lookup"><span data-stu-id="0644f-661">Tai\_Tham</span></span> |
| <span data-ttu-id="0644f-662">Tai\_Viet</span><span class="sxs-lookup"><span data-stu-id="0644f-662">Tai\_Viet</span></span> |
| <span data-ttu-id="0644f-663">Takri</span><span class="sxs-lookup"><span data-stu-id="0644f-663">Takri</span></span> |
| <span data-ttu-id="0644f-664">타밀어</span><span class="sxs-lookup"><span data-stu-id="0644f-664">Tamil</span></span> |
| <span data-ttu-id="0644f-665">탕구트 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-665">Tangut</span></span> |
| <span data-ttu-id="0644f-666">텔루구어</span><span class="sxs-lookup"><span data-stu-id="0644f-666">Telugu</span></span> |
| <span data-ttu-id="0644f-667">타아나 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-667">Thaana</span></span> |
| <span data-ttu-id="0644f-668">태국어</span><span class="sxs-lookup"><span data-stu-id="0644f-668">Thai</span></span> |
| <span data-ttu-id="0644f-669">티베트어</span><span class="sxs-lookup"><span data-stu-id="0644f-669">Tibetan</span></span> |
| <span data-ttu-id="0644f-670">티푸나구 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-670">Tifinagh</span></span> |
| <span data-ttu-id="0644f-671">티 루타 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-671">Tirhuta</span></span> |
| <span data-ttu-id="0644f-672">우가리아어</span><span class="sxs-lookup"><span data-stu-id="0644f-672">Ugaritic</span></span> |
| <span data-ttu-id="0644f-673">바이</span><span class="sxs-lookup"><span data-stu-id="0644f-673">Vai</span></span> |
| <span data-ttu-id="0644f-674">완초 문자</span><span class="sxs-lookup"><span data-stu-id="0644f-674">Wancho</span></span> |
| <span data-ttu-id="0644f-675">Warang\_Citi</span><span class="sxs-lookup"><span data-stu-id="0644f-675">Warang\_Citi</span></span> |
| <span data-ttu-id="0644f-676">Yezidi</span><span class="sxs-lookup"><span data-stu-id="0644f-676">Yezidi</span></span> |
| <span data-ttu-id="0644f-677">이어</span><span class="sxs-lookup"><span data-stu-id="0644f-677">Yi</span></span> |
| <span data-ttu-id="0644f-678">Zanabazar\_Square</span><span class="sxs-lookup"><span data-stu-id="0644f-678">Zanabazar\_Square</span></span> |

|&nbsp;| <span data-ttu-id="0644f-679">Vim 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="0644f-679">Vim character classes</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-680">\i</span><span class="sxs-lookup"><span data-stu-id="0644f-680">\i</span></span> | <span data-ttu-id="0644f-681">식별자 문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-681">identifier character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-682">\I</span><span class="sxs-lookup"><span data-stu-id="0644f-682">\I</span></span> | <span data-ttu-id="0644f-683">\i 제외 숫자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-683">\i except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-684">\k</span><span class="sxs-lookup"><span data-stu-id="0644f-684">\k</span></span> | <span data-ttu-id="0644f-685">키워드 문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-685">keyword character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-686">\K</span><span class="sxs-lookup"><span data-stu-id="0644f-686">\K</span></span> | <span data-ttu-id="0644f-687">숫자를 제외한 \k(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-687">\k except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-688">\f</span><span class="sxs-lookup"><span data-stu-id="0644f-688">\f</span></span> | <span data-ttu-id="0644f-689">파일 이름 문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-689">file name character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-690">\F</span><span class="sxs-lookup"><span data-stu-id="0644f-690">\F</span></span> | <span data-ttu-id="0644f-691">\f 숫자 제외(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-691">\f except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-692">\p</span><span class="sxs-lookup"><span data-stu-id="0644f-692">\p</span></span> | <span data-ttu-id="0644f-693">인쇄 가능한 문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-693">printable character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-694">\P</span><span class="sxs-lookup"><span data-stu-id="0644f-694">\P</span></span> | <span data-ttu-id="0644f-695">\p 숫자 제외(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-695">\p except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-696">\s</span><span class="sxs-lookup"><span data-stu-id="0644f-696">\s</span></span> | <span data-ttu-id="0644f-697">공백 문자([\t])(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-697">whitespace character (≡ [\t]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-698">\S</span><span class="sxs-lookup"><span data-stu-id="0644f-698">\S</span></span> | <span data-ttu-id="0644f-699">공백 문자가 아닌 문자([^ \t])(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-699">non-white space character (≡ [^ \t]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-700">\d</span><span class="sxs-lookup"><span data-stu-id="0644f-700">\d</span></span> | <span data-ttu-id="0644f-701">숫자(숫자 [0-9]) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-701">digits (≡ [0-9]) VIM</span></span> |
| <span data-ttu-id="0644f-702">\D</span><span class="sxs-lookup"><span data-stu-id="0644f-702">\D</span></span> | <span data-ttu-id="0644f-703">\d VIM이 아님</span><span class="sxs-lookup"><span data-stu-id="0644f-703">not \d VIM</span></span> |
| <span data-ttu-id="0644f-704">\x</span><span class="sxs-lookup"><span data-stu-id="0644f-704">\x</span></span> | <span data-ttu-id="0644f-705">16진수([0-9A-Fa-f])(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-705">hex digits (≡ [0-9A-Fa-f]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-706">\X</span><span class="sxs-lookup"><span data-stu-id="0644f-706">\X</span></span> | <span data-ttu-id="0644f-707">\x 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-707">not \x (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-708">\o</span><span class="sxs-lookup"><span data-stu-id="0644f-708">\o</span></span> | <span data-ttu-id="0644f-709">8진수([0-7])(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-709">octal digits (≡ [0-7]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-710">\O</span><span class="sxs-lookup"><span data-stu-id="0644f-710">\O</span></span> | <span data-ttu-id="0644f-711">\o(지원되지 않음) VIM 아님</span><span class="sxs-lookup"><span data-stu-id="0644f-711">not \o (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-712">\w</span><span class="sxs-lookup"><span data-stu-id="0644f-712">\w</span></span> | <span data-ttu-id="0644f-713">단어 문자 VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-713">word character VIM</span></span> |
| <span data-ttu-id="0644f-714">\W</span><span class="sxs-lookup"><span data-stu-id="0644f-714">\W</span></span> | <span data-ttu-id="0644f-715">not \w VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-715">not \w VIM</span></span> |
| <span data-ttu-id="0644f-716">\h</span><span class="sxs-lookup"><span data-stu-id="0644f-716">\h</span></span> | <span data-ttu-id="0644f-717">단어 문자(지원되지 않음) 헤드 VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-717">head of word character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-718">\H</span><span class="sxs-lookup"><span data-stu-id="0644f-718">\H</span></span> | <span data-ttu-id="0644f-719">\h(지원되지 않음) VIM 아님</span><span class="sxs-lookup"><span data-stu-id="0644f-719">not \h (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-720">\a</span><span class="sxs-lookup"><span data-stu-id="0644f-720">\a</span></span> | <span data-ttu-id="0644f-721">영문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-721">alphabetic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-722">\A</span><span class="sxs-lookup"><span data-stu-id="0644f-722">\A</span></span> | <span data-ttu-id="0644f-723">\a 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-723">not \a (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-724">\l</span><span class="sxs-lookup"><span data-stu-id="0644f-724">\l</span></span> | <span data-ttu-id="0644f-725">소문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-725">lowercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-726">\L</span><span class="sxs-lookup"><span data-stu-id="0644f-726">\L</span></span> | <span data-ttu-id="0644f-727">소문자 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-727">not lowercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-728">\u</span><span class="sxs-lookup"><span data-stu-id="0644f-728">\u</span></span> | <span data-ttu-id="0644f-729">대문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-729">uppercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-730">\U</span><span class="sxs-lookup"><span data-stu-id="0644f-730">\U</span></span> | <span data-ttu-id="0644f-731">대문자 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-731">not uppercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-732">\_x</span><span class="sxs-lookup"><span data-stu-id="0644f-732">\_x</span></span> | <span data-ttu-id="0644f-733">\x+줄 바꿈, 모든 x(지원되지 않음) VIM용</span><span class="sxs-lookup"><span data-stu-id="0644f-733">\x plus newline, for any x (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-734">\c</span><span class="sxs-lookup"><span data-stu-id="0644f-734">\c</span></span> | <span data-ttu-id="0644f-735">대/소문자 무시(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-735">ignore case (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-736">\C</span><span class="sxs-lookup"><span data-stu-id="0644f-736">\C</span></span> | <span data-ttu-id="0644f-737">대/소문자 일치(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-737">match case (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-738">\m</span><span class="sxs-lookup"><span data-stu-id="0644f-738">\m</span></span> | <span data-ttu-id="0644f-739">마법(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-739">magic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-740">\M</span><span class="sxs-lookup"><span data-stu-id="0644f-740">\M</span></span> | <span data-ttu-id="0644f-741">마법 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-741">nomagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-742">\v</span><span class="sxs-lookup"><span data-stu-id="0644f-742">\v</span></span> | <span data-ttu-id="0644f-743">VIM(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-743">verymagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-744">\V</span><span class="sxs-lookup"><span data-stu-id="0644f-744">\V</span></span> | <span data-ttu-id="0644f-745">verynomagic(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="0644f-745">verynomagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="0644f-746">\Z</span><span class="sxs-lookup"><span data-stu-id="0644f-746">\Z</span></span> | <span data-ttu-id="0644f-747">유니코드 조합 문자(지원되지 않음) VIM의 차이 무시</span><span class="sxs-lookup"><span data-stu-id="0644f-747">ignore differences in Unicode combining characters (NOT SUPPORTED) VIM</span></span> |

| &nbsp; | <span data-ttu-id="0644f-748">매직</span><span class="sxs-lookup"><span data-stu-id="0644f-748">Magic</span></span> |
| --- | --- |
| <span data-ttu-id="0644f-749">(?{code})</span><span class="sxs-lookup"><span data-stu-id="0644f-749">(?{code})</span></span> | <span data-ttu-id="0644f-750">임의 Perl 코드(지원되지 않음) PERL</span><span class="sxs-lookup"><span data-stu-id="0644f-750">arbitrary Perl code (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="0644f-751">(?{code})</span><span class="sxs-lookup"><span data-stu-id="0644f-751">(??{code})</span></span> | <span data-ttu-id="0644f-752">지연된 임의 Perl 코드(지원되지 않음) PERL</span><span class="sxs-lookup"><span data-stu-id="0644f-752">postponed arbitrary Perl code (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="0644f-753">(?n)</span><span class="sxs-lookup"><span data-stu-id="0644f-753">(?n)</span></span> | <span data-ttu-id="0644f-754">그룹 n을 캡처하기 위한 재귀 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-754">recursive call to regexp capturing group n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-755">(?+n)</span><span class="sxs-lookup"><span data-stu-id="0644f-755">(?+n)</span></span> | <span data-ttu-id="0644f-756">상대 그룹에 대한 재귀 호출 +n(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-756">recursive call to relative group +n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-757">(?-n)</span><span class="sxs-lookup"><span data-stu-id="0644f-757">(?-n)</span></span> | <span data-ttu-id="0644f-758">상대 그룹에 대한 재귀 호출 -n(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-758">recursive call to relative group -n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-759">(?C)</span><span class="sxs-lookup"><span data-stu-id="0644f-759">(?C)</span></span> | <span data-ttu-id="0644f-760">PCRE 콜아웃(지원되지 않음) PCRE</span><span class="sxs-lookup"><span data-stu-id="0644f-760">PCRE callout (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="0644f-761">(?R)</span><span class="sxs-lookup"><span data-stu-id="0644f-761">(?R)</span></span> | <span data-ttu-id="0644f-762">전체 regexp(?0)에 대한 재귀 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-762">recursive call to entire regexp (≡ (?0)) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-763">(?&amp;name)</span><span class="sxs-lookup"><span data-stu-id="0644f-763">(?&amp;name)</span></span> | <span data-ttu-id="0644f-764">명명된 그룹에 대한 재귀 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-764">recursive call to named group (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-765">(?P=이름)</span><span class="sxs-lookup"><span data-stu-id="0644f-765">(?P=name)</span></span> | <span data-ttu-id="0644f-766">명명된 역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-766">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-767">(?P&gt;name)</span><span class="sxs-lookup"><span data-stu-id="0644f-767">(?P&gt;name)</span></span> | <span data-ttu-id="0644f-768">명명된 그룹에 대한 재귀 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-768">recursive call to named group (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-769">(?(조건)true</span><span class="sxs-lookup"><span data-stu-id="0644f-769">(?(cond)true</span></span>|<span data-ttu-id="0644f-770">false)</span><span class="sxs-lookup"><span data-stu-id="0644f-770">false)</span></span> | <span data-ttu-id="0644f-771">조건부 분기(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-771">conditional branch (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-772">(?(조건)true)</span><span class="sxs-lookup"><span data-stu-id="0644f-772">(?(cond)true)</span></span> | <span data-ttu-id="0644f-773">조건부 분기(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-773">conditional branch (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-774">(\*ACCEPT)</span><span class="sxs-lookup"><span data-stu-id="0644f-774">(\*ACCEPT)</span></span> | <span data-ttu-id="0644f-775">regexps를 Prolog와 유사하게 만들기(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-775">make regexps more like Prolog (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-776">(\*COMMIT)</span><span class="sxs-lookup"><span data-stu-id="0644f-776">(\*COMMIT)</span></span> | <span data-ttu-id="0644f-777">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-777">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-778">(\*F)</span><span class="sxs-lookup"><span data-stu-id="0644f-778">(\*F)</span></span> | <span data-ttu-id="0644f-779">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-779">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-780">(\*FAIL)</span><span class="sxs-lookup"><span data-stu-id="0644f-780">(\*FAIL)</span></span> | <span data-ttu-id="0644f-781">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-781">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-782">(\*MARK)</span><span class="sxs-lookup"><span data-stu-id="0644f-782">(\*MARK)</span></span> | <span data-ttu-id="0644f-783">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-783">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-784">(\*PRUNE)</span><span class="sxs-lookup"><span data-stu-id="0644f-784">(\*PRUNE)</span></span> | <span data-ttu-id="0644f-785">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-785">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-786">(\*SKIP)</span><span class="sxs-lookup"><span data-stu-id="0644f-786">(\*SKIP)</span></span> | <span data-ttu-id="0644f-787">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-787">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-788">(\*THEN)</span><span class="sxs-lookup"><span data-stu-id="0644f-788">(\*THEN)</span></span> | <span data-ttu-id="0644f-789">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-789">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-790">(\*Any)</span><span class="sxs-lookup"><span data-stu-id="0644f-790">(\*ANY)</span></span> | <span data-ttu-id="0644f-791">줄바꿈 규칙 설정 (지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-791">set newline convention (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-792">(\*AnyCRLF)</span><span class="sxs-lookup"><span data-stu-id="0644f-792">(\*ANYCRLF)</span></span> | <span data-ttu-id="0644f-793">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-793">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-794">(\*CR)</span><span class="sxs-lookup"><span data-stu-id="0644f-794">(\*CR)</span></span> | <span data-ttu-id="0644f-795">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-795">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-796">(\*CRLF)</span><span class="sxs-lookup"><span data-stu-id="0644f-796">(\*CRLF)</span></span> | <span data-ttu-id="0644f-797">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-797">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-798">(\*LF)</span><span class="sxs-lookup"><span data-stu-id="0644f-798">(\*LF)</span></span> | <span data-ttu-id="0644f-799">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0644f-799">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="0644f-800">(\*BSR\_ANYCRLF)</span><span class="sxs-lookup"><span data-stu-id="0644f-800">(\*BSR\_ANYCRLF)</span></span> | <span data-ttu-id="0644f-801">\R 컨벤션(지원되지 않음) PCRE 설정</span><span class="sxs-lookup"><span data-stu-id="0644f-801">set \R convention (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="0644f-802">(\*BSR\_UNICODE)</span><span class="sxs-lookup"><span data-stu-id="0644f-802">(\*BSR\_UNICODE)</span></span> | <span data-ttu-id="0644f-803">(지원되지 않음) PCRE</span><span class="sxs-lookup"><span data-stu-id="0644f-803">(NOT SUPPORTED) PCRE</span></span> |

## <a name="content-license"></a><span data-ttu-id="0644f-804">콘텐츠 라이선스</span><span class="sxs-lookup"><span data-stu-id="0644f-804">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="0644f-805">이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-805">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="0644f-806">원래 페이지는 [여기](https://github.com/google/re2/wiki/Syntax)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-806">The original page can be found [here](https://github.com/google/re2/wiki/Syntax).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="0644f-807">이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0644f-807">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0644f-808">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0644f-808">See also</span></span>

- [<span data-ttu-id="0644f-809">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="0644f-809">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)