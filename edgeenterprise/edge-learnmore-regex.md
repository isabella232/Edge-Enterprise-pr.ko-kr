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
ms.openlocfilehash: 9654a25d2c0474601fb719b145ebb1f59241a6d9
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980668"
---
# <span data-ttu-id="1e4d9-103">정규식 2(re2.h) 구문</span><span class="sxs-lookup"><span data-stu-id="1e4d9-103">Regular Expression 2 (re2.h) syntax</span></span>

<span data-ttu-id="1e4d9-104">정규식은 문자열 세트를 설명하기 위한 표기법입니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-104">Regular expressions are a notation for describing sets of character strings.</span></span> <span data-ttu-id="1e4d9-105">문자열이 정규식으로 설명된 집합에 있을 때 정규식이 문자열과 일치한다고 종종 말합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-105">When a string is in the set described by a regular expression, we often say that the regular expression matches the string.</span></span>

<span data-ttu-id="1e4d9-106">가장 간단한 정규식은 단일 리터럴 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-106">The simplest regular expression is a single literal character.</span></span> <span data-ttu-id="1e4d9-107">*\*+?()|* 과 같은 메타 문자를 제외하고 문자는 자신과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-107">Except for the metacharacters like *\*+?()|*, characters match themselves.</span></span> <span data-ttu-id="1e4d9-108">메타 문자를 일치 시키려면 백 슬래시로 이스케이프하세요. \+는 리터럴 더하기 문자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-108">To match a metacharacter, escape it with a backslash: \+ matches a literal plus character.</span></span>

<span data-ttu-id="1e4d9-109">두 개의 정규식을 변경하거나 연결하여 새 정규식을 형성할 수 있습니다.*e<sub>1</sub>* 이 _s_ 및 \* e <sub>2</sub>와 일치하는 경우 *는 _t_와 일치하고 *e<sub>1</sub>* | \* e <sub>2</sub>* 은 _ s<와 일치합니다. _ 또는 _t_, *e<sub>1</sub>* \* e <sub>2</sub> \*은 _ st_와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-109">Two regular expressions can be altered or concatenated to form a new regular expression: if *e<sub>1</sub>* matches _s_ and *e<sub>2</sub>* matches _t_, then *e<sub>1</sub>* | *e<sub>2</sub>* matches _s_ or _t_, and *e<sub>1</sub>* *e<sub>2</sub>*  matches _st_.</span></span>

<span data-ttu-id="1e4d9-110">메타 문자 _ \* _, _ + _ 및 _? _</span><span class="sxs-lookup"><span data-stu-id="1e4d9-110">The metacharacters _\*_ , _+_ , and _?_</span></span> <span data-ttu-id="1e4d9-111">반복 연산자입니다: *e<sub>1</sub>*_ \*_ 는 0개 이상의 (아마도 다른) 문자열의 시퀀스와 일치하며 각각 \* e<sub>과 일치합니다. 1</sub> *; \* e <sub>1</sub> \* _ + _는 하나 이상과 일치합니다.*e<sub>1</sub>\* _? _</span><span class="sxs-lookup"><span data-stu-id="1e4d9-111">are repetition operators: *e<sub>1</sub>* _\*_ matches a sequence of zero or more (possibly different) strings, each of which match *e<sub>1</sub>*; *e<sub>1</sub>* _+_ matches one or more; *e<sub>1</sub>* _?_</span></span> <span data-ttu-id="1e4d9-112">0 또는 1과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-112">matches zero or one.</span></span>

<span data-ttu-id="1e4d9-113">가장 약한 바인딩에서 가장 강한 바인딩까지 연산자 우선 순위는 먼저 교대, 다음 연결, 마지막으로 반복 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-113">The operator precedence, from weakest to strongest binding, is first alternation, then concatenation, and finally the repetition operators.</span></span> <span data-ttu-id="1e4d9-114">산술식에서와 같이 명시적 괄호를 사용하여 다르게 의미를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-114">Explicit parentheses can be used to force different meanings, just as in arithmetic expressions.</span></span> <span data-ttu-id="1e4d9-115">몇 가지 예: _ab|cd_은 _(ab)|(cd)_ 와 같습니다. _ab\*_ 는 _a(b\*)_ 와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-115">Some examples: _ab|cd_ is equivalent to _(ab)|(cd)_ ; _ab\*_ is equivalent to _a(b\*)_ .</span></span>

<span data-ttu-id="1e4d9-116">지금까지 설명한 구문은 대부분의 기존 Unix _egrep_ 정규식 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-116">The syntax described so far is most of the traditional Unix _egrep_ regular expression syntax.</span></span> <span data-ttu-id="1e4d9-117">이 하위 집합은 모든 일반 언어를 설명하는 데 충분합니다. 대략적으로하게 말하면 일반 언어는 고정된 양의 메모리만 사용하여 한 번에 텍스트를 통과하여 매칭될 수 있는 문자열 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-117">This subset suffices to describe all regular languages: loosely speaking, a regular language is a set of strings that can be matched in a single pass through the text using only a fixed amount of memory.</span></span> <span data-ttu-id="1e4d9-118">새로운 정규식 기능(Perl 및 이를 복사한 기능)은 수많은 새 연산자와 이스케이프 시퀀스를 추가했으며, 정규 표현식을 보다 간결하고, 때로는 암호화된 방식으로 만들기도 하지만 일반적으로 더 강력하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-118">Newer regular expression facilities (notably Perl and those that have copied it) have added many new operators and escape sequences, which make the regular expressions more concise, and sometimes more cryptic, but usually not more powerful.</span></span>

<span data-ttu-id="1e4d9-119">이 페이지는 RE2에서 허용하는 정규식 구문을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-119">This page lists the regular expression syntax accepted by RE2.</span></span>

<span data-ttu-id="1e4d9-120">또한 PCRE, PERL 및 VIM에서 허용하는 일부 구문을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-120">It also lists some syntax accepted by PCRE, PERL and VIM.</span></span>

## <span data-ttu-id="1e4d9-121">구문 테이블</span><span class="sxs-lookup"><span data-stu-id="1e4d9-121">Syntax tables</span></span>

| <span data-ttu-id="1e4d9-122">단일 문자 표현의 종류</span><span class="sxs-lookup"><span data-stu-id="1e4d9-122">Kinds of single-character expressions</span></span> | <span data-ttu-id="1e4d9-123">예</span><span class="sxs-lookup"><span data-stu-id="1e4d9-123">Examples</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-124">모든 문자, 줄 바꿈(s=true)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-124">any character, possibly including newline (s=true)</span></span> | <span data-ttu-id="1e4d9-125">.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-125">.</span></span> |
| <span data-ttu-id="1e4d9-126">문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-126">character class</span></span> | <span data-ttu-id="1e4d9-127">[xyz]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-127">[xyz]</span></span> |
| <span data-ttu-id="1e4d9-128">부정 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-128">negated character class</span></span> | <span data-ttu-id="1e4d9-129">[^xyz]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-129">[^xyz]</span></span> |
| <span data-ttu-id="1e4d9-130">Perl 문자 클래스([ 링크 ](#user-content-perl))</span><span class="sxs-lookup"><span data-stu-id="1e4d9-130">Perl character class ([link](#user-content-perl))</span></span> | <span data-ttu-id="1e4d9-131">\d</span><span class="sxs-lookup"><span data-stu-id="1e4d9-131">\d</span></span> |
| <span data-ttu-id="1e4d9-132">부정된 Perl 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-132">negated Perl character class</span></span> | <span data-ttu-id="1e4d9-133">\D</span><span class="sxs-lookup"><span data-stu-id="1e4d9-133">\D</span></span> |
| <span data-ttu-id="1e4d9-134">ASCII 문자 클래스([링크 ](#user-content-ascii))</span><span class="sxs-lookup"><span data-stu-id="1e4d9-134">ASCII character class ([link](#user-content-ascii))</span></span> | <span data-ttu-id="1e4d9-135">[[:alpha:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-135">[[:alpha:]]</span></span> |
| <span data-ttu-id="1e4d9-136">부정된 ASCII 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-136">negated ASCII character class</span></span> | <span data-ttu-id="1e4d9-137">[[:^alpha:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-137">[[:^alpha:]]</span></span> |
| <span data-ttu-id="1e4d9-138">유니코드 문자 클래스(한 글자 이름)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-138">Unicode character class (one-letter name)</span></span> | <span data-ttu-id="1e4d9-139">\pN</span><span class="sxs-lookup"><span data-stu-id="1e4d9-139">\pN</span></span> |
| <span data-ttu-id="1e4d9-140">유니코드 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-140">Unicode character class</span></span> | <span data-ttu-id="1e4d9-141">\p{Greek}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-141">\p{Greek}</span></span> |
| <span data-ttu-id="1e4d9-142">부정된 유니코드 문자 클래스(한 글자 이름)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-142">negated Unicode character class (one-letter name)</span></span> | <span data-ttu-id="1e4d9-143">\PN</span><span class="sxs-lookup"><span data-stu-id="1e4d9-143">\PN</span></span> |
| <span data-ttu-id="1e4d9-144">부정된 유니코드 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-144">negated Unicode character class</span></span> | <span data-ttu-id="1e4d9-145">\P{Greek}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-145">\P{Greek}</span></span> |

| | <span data-ttu-id="1e4d9-146">합성물</span><span class="sxs-lookup"><span data-stu-id="1e4d9-146">Composites</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-147">xy</span><span class="sxs-lookup"><span data-stu-id="1e4d9-147">xy</span></span> | <span data-ttu-id="1e4d9-148">x 다음에 y</span><span class="sxs-lookup"><span data-stu-id="1e4d9-148">x followed by y</span></span> |
| <span data-ttu-id="1e4d9-149">x\|y</span><span class="sxs-lookup"><span data-stu-id="1e4d9-149">x\|y</span></span> | <span data-ttu-id="1e4d9-150">x 또는 y(x 선호)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-150">x or y (prefer x)</span></span> |

| | <span data-ttu-id="1e4d9-151">반복</span><span class="sxs-lookup"><span data-stu-id="1e4d9-151">Repetitions</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-152">x\*</span><span class="sxs-lookup"><span data-stu-id="1e4d9-152">x\*</span></span> | <span data-ttu-id="1e4d9-153">0개 이상의 x, 더 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-153">zero or more x, prefer more</span></span> |
| <span data-ttu-id="1e4d9-154">x+</span><span class="sxs-lookup"><span data-stu-id="1e4d9-154">x+</span></span> | <span data-ttu-id="1e4d9-155">하나 이상의 x, 더 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-155">one or more x, prefer more</span></span> |
| <span data-ttu-id="1e4d9-156">x?</span><span class="sxs-lookup"><span data-stu-id="1e4d9-156">x?</span></span> | <span data-ttu-id="1e4d9-157">0 개 또는 1개의 x, 1개 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-157">zero or one x, prefer one</span></span> |
| <span data-ttu-id="1e4d9-158">x{n,m}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-158">x{n,m}</span></span> | <span data-ttu-id="1e4d9-159">n 또는 n+1 또는 ... 또는 m x, 더 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-159">n or n+1 or ... or m x, prefer more</span></span> |
| <span data-ttu-id="1e4d9-160">x{n,}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-160">x{n,}</span></span> | <span data-ttu-id="1e4d9-161">n개 이상의 x, 더 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-161">n or more x, prefer more</span></span> |
| <span data-ttu-id="1e4d9-162">x{n}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-162">x{n}</span></span> | <span data-ttu-id="1e4d9-163">정확히 n x</span><span class="sxs-lookup"><span data-stu-id="1e4d9-163">exactly n x</span></span> |
| <span data-ttu-id="1e4d9-164">x\*?</span><span class="sxs-lookup"><span data-stu-id="1e4d9-164">x\*?</span></span> | <span data-ttu-id="1e4d9-165">0개 이상의 x, 더 적은 것 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-165">zero or more x, prefer fewer</span></span> |
| <span data-ttu-id="1e4d9-166">x+?</span><span class="sxs-lookup"><span data-stu-id="1e4d9-166">x+?</span></span> | <span data-ttu-id="1e4d9-167">하나 이상의 x, 더 적은 것 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-167">one or more x, prefer fewer</span></span> |
| <span data-ttu-id="1e4d9-168">x??</span><span class="sxs-lookup"><span data-stu-id="1e4d9-168">x??</span></span> | <span data-ttu-id="1e4d9-169">0 또는 1 x, 0 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-169">zero or one x, prefer zero</span></span> |
| <span data-ttu-id="1e4d9-170">x{n,m}?</span><span class="sxs-lookup"><span data-stu-id="1e4d9-170">x{n,m}?</span></span> | <span data-ttu-id="1e4d9-171">n 또는 n+1 또는 ... 또는 m x, 더 적은 것 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-171">n or n+1 or ... or m x, prefer fewer</span></span> |
| <span data-ttu-id="1e4d9-172">x {n,}?</span><span class="sxs-lookup"><span data-stu-id="1e4d9-172">x{n,}?</span></span> | <span data-ttu-id="1e4d9-173">n개 이상의 x, 더 적은 것 선호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-173">n or more x, prefer fewer</span></span> |
| <span data-ttu-id="1e4d9-174">x{n}?</span><span class="sxs-lookup"><span data-stu-id="1e4d9-174">x{n}?</span></span> | <span data-ttu-id="1e4d9-175">정확히 n x</span><span class="sxs-lookup"><span data-stu-id="1e4d9-175">exactly n x</span></span> |
| <span data-ttu-id="1e4d9-176">x{}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-176">x{}</span></span> | <span data-ttu-id="1e4d9-177">(≡ x\*) (지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-177">(≡ x\*) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-178">x{-}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-178">x{-}</span></span> | <span data-ttu-id="1e4d9-179">(≡x\*?) (지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-179">(≡ x\*?) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-180">x{-n}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-180">x{-n}</span></span> | <span data-ttu-id="1e4d9-181">(≡x{n}?) (지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-181">(≡ x{n}?) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-182">x=</span><span class="sxs-lookup"><span data-stu-id="1e4d9-182">x=</span></span> | <span data-ttu-id="1e4d9-183">(≡x?) (지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-183">(≡ x?) (NOT SUPPORTED) VIM</span></span> |

<span data-ttu-id="1e4d9-184">구현 제한 : 계산 양식 x{n,m}, x{n,}, 및 x{n}은 최소 또는 최대 반복 횟수를 1000 이상으로 만드는 양식을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-184">Implementation restriction: The counting forms x{n,m}, x{n,}, and x{n} reject forms that create a minimum or maximum repetition count above 1000.</span></span> <span data-ttu-id="1e4d9-185">무제한 반복에는 이 제한이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-185">Unlimited repetitions are not subject to this restriction.</span></span>

| | <span data-ttu-id="1e4d9-186">소유 반복</span><span class="sxs-lookup"><span data-stu-id="1e4d9-186">Possessive repetitions</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-187">x\*+</span><span class="sxs-lookup"><span data-stu-id="1e4d9-187">x\*+</span></span> | <span data-ttu-id="1e4d9-188">0개 이상의 x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-188">zero or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-189">x++</span><span class="sxs-lookup"><span data-stu-id="1e4d9-189">x++</span></span> | <span data-ttu-id="1e4d9-190">하나 이상의 x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-190">one or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-191">x?+</span><span class="sxs-lookup"><span data-stu-id="1e4d9-191">x?+</span></span> | <span data-ttu-id="1e4d9-192">0개 또는 1개의 x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-192">zero or one x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-193">x{n,m}+</span><span class="sxs-lookup"><span data-stu-id="1e4d9-193">x{n,m}+</span></span> | <span data-ttu-id="1e4d9-194">n 또는 ... 또는 m x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-194">n or ... or m x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-195">x{n,}+</span><span class="sxs-lookup"><span data-stu-id="1e4d9-195">x{n,}+</span></span> | <span data-ttu-id="1e4d9-196">n개 이상의 x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-196">n or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-197">x{n}+</span><span class="sxs-lookup"><span data-stu-id="1e4d9-197">x{n}+</span></span> | <span data-ttu-id="1e4d9-198">정확히 n x, 소유격(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-198">exactly n x, possessive (NOT SUPPORTED)</span></span> |

| | <span data-ttu-id="1e4d9-199">그룹화</span><span class="sxs-lookup"><span data-stu-id="1e4d9-199">Grouping</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-200">(re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-200">(re)</span></span> | <span data-ttu-id="1e4d9-201">번호가 매겨진 캡처링 그룹(부분 일치)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-201">numbered capturing group (submatch)</span></span> |
| <span data-ttu-id="1e4d9-202">(?P&lt;이름&gt;re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-202">(?P&lt;name&gt;re)</span></span> | <span data-ttu-id="1e4d9-203">&amp;(으)로 명명된 번호가 매겨진 캡처링 그룹(부분 일치)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-203">named &amp; numbered capturing group (submatch)</span></span> |
| <span data-ttu-id="1e4d9-204">(?&lt;이름&gt;re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-204">(?&lt;name&gt;re)</span></span> | <span data-ttu-id="1e4d9-205">&amp;(으)로 명명된 번호가 매겨진 캡처링 그룹(부분 일치)(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-205">named &amp; numbered capturing group (submatch) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-206">(?&#39;이름&#39;re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-206">(?&#39;name&#39;re)</span></span> | <span data-ttu-id="1e4d9-207">&amp;(으)로 명명된 번호가 매겨진 캡처링 그룹(부분 일치)(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-207">named &amp; numbered capturing group (submatch) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-208">(?:re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-208">(?:re)</span></span> | <span data-ttu-id="1e4d9-209">비 캡처링 그룹</span><span class="sxs-lookup"><span data-stu-id="1e4d9-209">non-capturing group</span></span> |
| <span data-ttu-id="1e4d9-210">(?flags)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-210">(?flags)</span></span> | <span data-ttu-id="1e4d9-211">현재 그룹 내에서 플래그를 설정합니다. 비 캡처링</span><span class="sxs-lookup"><span data-stu-id="1e4d9-211">set flags within current group; non-capturing</span></span> |
| <span data-ttu-id="1e4d9-212">(?flags:re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-212">(?flags:re)</span></span> | <span data-ttu-id="1e4d9-213">다시 수행하는 동안 플래그를 설정합니다. 비 캡처링</span><span class="sxs-lookup"><span data-stu-id="1e4d9-213">set flags during re; non-capturing</span></span> |
| <span data-ttu-id="1e4d9-214">(?#text)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-214">(?#text)</span></span> | <span data-ttu-id="1e4d9-215">메모(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-215">comment (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-216">(?\|x\|y\|z)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-216">(?\|x\|y\|z)</span></span> | <span data-ttu-id="1e4d9-217">분기 번호 매기기 재설정(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-217">branch numbering reset (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-218">(?&gt;re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-218">(?&gt;re)</span></span> | <span data-ttu-id="1e4d9-219">re (지원되지 않음)의 소유격 일치 결과</span><span class="sxs-lookup"><span data-stu-id="1e4d9-219">possessive match of re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-220">re@&gt;</span><span class="sxs-lookup"><span data-stu-id="1e4d9-220">re@&gt;</span></span> | <span data-ttu-id="1e4d9-221">re (지원되지 않음)의 소유격 일치 결과 VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-221">possessive match of re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-222">%(re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-222">%(re)</span></span> | <span data-ttu-id="1e4d9-223">비 캡처링 그룹(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-223">non-capturing group (NOT SUPPORTED) VIM</span></span> |

| | <span data-ttu-id="1e4d9-224">Flags</span><span class="sxs-lookup"><span data-stu-id="1e4d9-224">Flags</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-225">i</span><span class="sxs-lookup"><span data-stu-id="1e4d9-225">i</span></span> | <span data-ttu-id="1e4d9-226">대/소문자를 구분하지 않습니다(기본값 false).</span><span class="sxs-lookup"><span data-stu-id="1e4d9-226">case-insensitive (default false)</span></span> |
| <span data-ttu-id="1e4d9-227">m</span><span class="sxs-lookup"><span data-stu-id="1e4d9-227">m</span></span> | <span data-ttu-id="1e4d9-228">여러 줄 모드: ^ 및 $는 시작/끝 텍스트 외에 시작/끝 줄과 일치합니다(기본값은 false).</span><span class="sxs-lookup"><span data-stu-id="1e4d9-228">multi-line mode: ^ and $ match begin/end line in addition to begin/end text (default false)</span></span> |
| <span data-ttu-id="1e4d9-229">s</span><span class="sxs-lookup"><span data-stu-id="1e4d9-229">s</span></span> | <span data-ttu-id="1e4d9-230">허용.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-230">let .</span></span> <span data-ttu-id="1e4d9-231">\n 치(기값 false)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-231">match \n (default false)</span></span> |
| <span data-ttu-id="1e4d9-232">U</span><span class="sxs-lookup"><span data-stu-id="1e4d9-232">U</span></span> | <span data-ttu-id="1e4d9-233">ungreedy: x\*와 x\*?, x+ 및 x+? 등의 의미를 바꿉니다(기본값 false).</span><span class="sxs-lookup"><span data-stu-id="1e4d9-233">ungreedy: swap meaning of x\* and x\*?, x+ and x+?, etc (default false)</span></span> |

<span data-ttu-id="1e4d9-234">Flag 구문에서 xyz(설정) 또는-xyz(c제거) 는 xy z (xy 설정,z 제거)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-234">Flag syntax is xyz (set) or -xyz (clear) or xy-z (set xy, clear z).</span></span>

|  | <span data-ttu-id="1e4d9-235">빈 문자열</span><span class="sxs-lookup"><span data-stu-id="1e4d9-235">Empty strings</span></span> |
| --- | --- |
| ^ | <span data-ttu-id="1e4d9-236">텍스트나 줄의 맨 앞(m = true)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-236">at beginning of text or line (m=true)</span></span> |
| $ | <span data-ttu-id="1e4d9-237">행 끝(\z not \Z) 또는 회선(m = true)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-237">at end of text (like \z not \Z) or line (m=true)</span></span> |
| <span data-ttu-id="1e4d9-238">\A</span><span class="sxs-lookup"><span data-stu-id="1e4d9-238">\A</span></span> | <span data-ttu-id="1e4d9-239">텍스트의 시작 부분에</span><span class="sxs-lookup"><span data-stu-id="1e4d9-239">at beginning of text</span></span> |
| <span data-ttu-id="1e4d9-240">\b</span><span class="sxs-lookup"><span data-stu-id="1e4d9-240">\b</span></span> | <span data-ttu-id="1e4d9-241">ASCII 단어 경계(1면과 \W, \A 또는 \z에 \w)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-241">at ASCII word boundary (\w on one side and \W, \A, or \z on the other)</span></span> |
| <span data-ttu-id="1e4d9-242">\B</span><span class="sxs-lookup"><span data-stu-id="1e4d9-242">\B</span></span> | <span data-ttu-id="1e4d9-243">ASCII 단어 경계가 아님</span><span class="sxs-lookup"><span data-stu-id="1e4d9-243">not at ASCII word boundary</span></span> |
| <span data-ttu-id="1e4d9-244">\g</span><span class="sxs-lookup"><span data-stu-id="1e4d9-244">\g</span></span> | <span data-ttu-id="1e4d9-245">검색 중인 하위 텍스트(지원되지 않음)의 시작 부분 PCRE</span><span class="sxs-lookup"><span data-stu-id="1e4d9-245">at beginning of subtext being searched (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="1e4d9-246">\G</span><span class="sxs-lookup"><span data-stu-id="1e4d9-246">\G</span></span> | <span data-ttu-id="1e4d9-247">마지막 일치 항목(지원되지 않음)의 종료 부분 PERL</span><span class="sxs-lookup"><span data-stu-id="1e4d9-247">at end of last match (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="1e4d9-248">\Z</span><span class="sxs-lookup"><span data-stu-id="1e4d9-248">\Z</span></span> | <span data-ttu-id="1e4d9-249">텍스트의 끝 또는 텍스트의 끝과 줄 바꿈 이전(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-249">at end of text, or before newline at end of text (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-250">\z</span><span class="sxs-lookup"><span data-stu-id="1e4d9-250">\z</span></span> | <span data-ttu-id="1e4d9-251">텍스트 끝</span><span class="sxs-lookup"><span data-stu-id="1e4d9-251">at end of text</span></span> |
| <span data-ttu-id="1e4d9-252">(?=re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-252">(?=re)</span></span> | <span data-ttu-id="1e4d9-253">텍스트 일치 이전(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-253">before text matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-254">%(re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-254">(?!re)</span></span> | <span data-ttu-id="1e4d9-255">텍스트 불일치 이전(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-255">before text not matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-256">(?&lt;=re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-256">(?&lt;=re)</span></span> | <span data-ttu-id="1e4d9-257">텍스트 일치(지원되지 않음) 전에</span><span class="sxs-lookup"><span data-stu-id="1e4d9-257">after text matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-258">(?&lt;!re)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-258">(?&lt;!re)</span></span> | <span data-ttu-id="1e4d9-259">텍스트 불일치 후에(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-259">after text not matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-260">re&amp;</span><span class="sxs-lookup"><span data-stu-id="1e4d9-260">re&amp;</span></span> | <span data-ttu-id="1e4d9-261">텍스트 일치 이전(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-261">before text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-262">re@=</span><span class="sxs-lookup"><span data-stu-id="1e4d9-262">re@=</span></span> | <span data-ttu-id="1e4d9-263">텍스트 일치 이전(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-263">before text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-264">re@!</span><span class="sxs-lookup"><span data-stu-id="1e4d9-264">re@!</span></span> | <span data-ttu-id="1e4d9-265">텍스트 불일치 이전(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-265">before text not matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-266">re@&lt;=</span><span class="sxs-lookup"><span data-stu-id="1e4d9-266">re@&lt;=</span></span> | <span data-ttu-id="1e4d9-267">텍스트 일치 이전(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-267">after text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-268">re@&lt;!</span><span class="sxs-lookup"><span data-stu-id="1e4d9-268">re@&lt;!</span></span> | <span data-ttu-id="1e4d9-269">텍스트 불일치 후(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-269">after text not matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-270">\zs</span><span class="sxs-lookup"><span data-stu-id="1e4d9-270">\zs</span></span> | <span data-ttu-id="1e4d9-271">일치 시작 설정(=\K)(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-271">sets start of match (= \K) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-272">\ze</span><span class="sxs-lookup"><span data-stu-id="1e4d9-272">\ze</span></span> | <span data-ttu-id="1e4d9-273">일치 종료 설정(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-273">sets end of match (NOT SUPPORTED) VIM</span></span> |
| \%^ | <span data-ttu-id="1e4d9-274">파일의 시작(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-274">beginning of file (NOT SUPPORTED) VIM</span></span> |
| \%$ | <span data-ttu-id="1e4d9-275">파일의 시작(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-275">end of file (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-276">\%V</span><span class="sxs-lookup"><span data-stu-id="1e4d9-276">\%V</span></span> | <span data-ttu-id="1e4d9-277">화면에서(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-277">on screen (NOT SUPPORTED) VIM</span></span> |
| \%# | <span data-ttu-id="1e4d9-278">커서 위치(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-278">cursor position (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-279">\%&#39;m</span><span class="sxs-lookup"><span data-stu-id="1e4d9-279">\%&#39;m</span></span> | <span data-ttu-id="1e4d9-280">m 위치 표시(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-280">mark m position (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-281">\%23l</span><span class="sxs-lookup"><span data-stu-id="1e4d9-281">\%23l</span></span> | <span data-ttu-id="1e4d9-282">회선 23에서(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-282">in line 23 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-283">\%23c</span><span class="sxs-lookup"><span data-stu-id="1e4d9-283">\%23c</span></span> | <span data-ttu-id="1e4d9-284">열 23에서(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-284">in column 23 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-285">\%23v</span><span class="sxs-lookup"><span data-stu-id="1e4d9-285">\%23v</span></span> | <span data-ttu-id="1e4d9-286">가상 열 23에서(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-286">in virtual column 23 (NOT SUPPORTED) VIM</span></span> |

|  | <span data-ttu-id="1e4d9-287">이스케이프 시퀀스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-287">Escape sequences</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-288">\a</span><span class="sxs-lookup"><span data-stu-id="1e4d9-288">\a</span></span> | <span data-ttu-id="1e4d9-289">종(≡ \007)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-289">bell (≡ \007)</span></span> |
| <span data-ttu-id="1e4d9-290">\f</span><span class="sxs-lookup"><span data-stu-id="1e4d9-290">\f</span></span> | <span data-ttu-id="1e4d9-291">양식 피드(≡ \014)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-291">form feed (≡ \014)</span></span> |
| <span data-ttu-id="1e4d9-292">\t</span><span class="sxs-lookup"><span data-stu-id="1e4d9-292">\t</span></span> | <span data-ttu-id="1e4d9-293">수평 탭(≡ \011)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-293">horizontal tab (≡ \011)</span></span> |
| <span data-ttu-id="1e4d9-294">\n</span><span class="sxs-lookup"><span data-stu-id="1e4d9-294">\n</span></span> | <span data-ttu-id="1e4d9-295">줄 바꿈(≡ \012)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-295">newline (≡ \012)</span></span> |
| <span data-ttu-id="1e4d9-296">\r</span><span class="sxs-lookup"><span data-stu-id="1e4d9-296">\r</span></span> | <span data-ttu-id="1e4d9-297">캐리지 반환(≡ \015)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-297">carriage return (≡ \015)</span></span> |
| <span data-ttu-id="1e4d9-298">\v</span><span class="sxs-lookup"><span data-stu-id="1e4d9-298">\v</span></span> | <span data-ttu-id="1e4d9-299">수직 탭 문자(≡ \013)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-299">vertical tab character (≡ \013)</span></span> |
| \* | <span data-ttu-id="1e4d9-300">literal \*, 모든 구두점 문자인 경우 \*</span><span class="sxs-lookup"><span data-stu-id="1e4d9-300">literal \*, for any punctuation character \*</span></span> |
| <span data-ttu-id="1e4d9-301">\123</span><span class="sxs-lookup"><span data-stu-id="1e4d9-301">\123</span></span> | <span data-ttu-id="1e4d9-302">8진수 문자 코드(최대 3자리)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-302">octal character code (up to three digits)</span></span> |
| <span data-ttu-id="1e4d9-303">\x7F</span><span class="sxs-lookup"><span data-stu-id="1e4d9-303">\x7F</span></span> | <span data-ttu-id="1e4d9-304">16진수 문자 코드(두 자리 수)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-304">hex character code (exactly two digits)</span></span> |
| <span data-ttu-id="1e4d9-305">\x{10FFF}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-305">\x{10FFFF}</span></span> | <span data-ttu-id="1e4d9-306">16진수 문자 코드</span><span class="sxs-lookup"><span data-stu-id="1e4d9-306">hex character code</span></span> |
| <span data-ttu-id="1e4d9-307">\C</span><span class="sxs-lookup"><span data-stu-id="1e4d9-307">\C</span></span> | <span data-ttu-id="1e4d9-308">UTF-8 모드에서도 단일 바이트 일치</span><span class="sxs-lookup"><span data-stu-id="1e4d9-308">match a single byte even in UTF-8 mode</span></span> |
| <span data-ttu-id="1e4d9-309">\Q...\E</span><span class="sxs-lookup"><span data-stu-id="1e4d9-309">\Q...\E</span></span> | <span data-ttu-id="1e4d9-310">리터럴 텍스트...문장 부호가 있더라도</span><span class="sxs-lookup"><span data-stu-id="1e4d9-310">literal text ... even if ... has punctuation</span></span> |
| <span data-ttu-id="1e4d9-311">\1</span><span class="sxs-lookup"><span data-stu-id="1e4d9-311">\1</span></span> | <span data-ttu-id="1e4d9-312">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-312">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-313">\b</span><span class="sxs-lookup"><span data-stu-id="1e4d9-313">\b</span></span> | <span data-ttu-id="1e4d9-314">백스페이스(지원되지 않음)(010원 사용)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-314">backspace (NOT SUPPORTED) (use \010)</span></span> |
| <span data-ttu-id="1e4d9-315">\cK</span><span class="sxs-lookup"><span data-stu-id="1e4d9-315">\cK</span></span> | <span data-ttu-id="1e4d9-316">제어 문자 ^K(지원되지 않음)(\001 등 사용)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-316">control char ^K (NOT SUPPORTED) (use \001 etc)</span></span> |
| <span data-ttu-id="1e4d9-317">\e</span><span class="sxs-lookup"><span data-stu-id="1e4d9-317">\e</span></span> | <span data-ttu-id="1e4d9-318">종료(지원되지 않음)(\033 사용)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-318">escape (NOT SUPPORTED) (use \033)</span></span> |
| <span data-ttu-id="1e4d9-319">\g1</span><span class="sxs-lookup"><span data-stu-id="1e4d9-319">\g1</span></span> | <span data-ttu-id="1e4d9-320">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-320">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-321">\g{1}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-321">\g{1}</span></span> | <span data-ttu-id="1e4d9-322">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-322">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-323">\g{+1}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-323">\g{+1}</span></span> | <span data-ttu-id="1e4d9-324">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-324">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-325">\g{-1}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-325">\g{-1}</span></span> | <span data-ttu-id="1e4d9-326">역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-326">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-327">\g{name}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-327">\g{name}</span></span> | <span data-ttu-id="1e4d9-328">명명된 백레퍼런스(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-328">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-329">\g&lt;name&gt;</span><span class="sxs-lookup"><span data-stu-id="1e4d9-329">\g&lt;name&gt;</span></span> | <span data-ttu-id="1e4d9-330">서브루틴 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-330">subroutine call (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-331">\g&#39;이름&#39;</span><span class="sxs-lookup"><span data-stu-id="1e4d9-331">\g&#39;name&#39;</span></span> | <span data-ttu-id="1e4d9-332">서브루틴 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-332">subroutine call (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-333">\k&lt;name&gt;</span><span class="sxs-lookup"><span data-stu-id="1e4d9-333">\k&lt;name&gt;</span></span> | <span data-ttu-id="1e4d9-334">명명된 백레퍼런스(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-334">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-335">\k&#39;name&#39;</span><span class="sxs-lookup"><span data-stu-id="1e4d9-335">\k&#39;name&#39;</span></span> | <span data-ttu-id="1e4d9-336">명명된 백레퍼런스(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-336">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-337">\lX</span><span class="sxs-lookup"><span data-stu-id="1e4d9-337">\lX</span></span> | <span data-ttu-id="1e4d9-338">소문자 X(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-338">lowercase X (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-339">\ux</span><span class="sxs-lookup"><span data-stu-id="1e4d9-339">\ux</span></span> | <span data-ttu-id="1e4d9-340">대문자 x(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-340">uppercase x (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-341">\L...\E</span><span class="sxs-lookup"><span data-stu-id="1e4d9-341">\L...\E</span></span> | <span data-ttu-id="1e4d9-342">소문자 텍스트...(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-342">lowercase text ... (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-343">\K</span><span class="sxs-lookup"><span data-stu-id="1e4d9-343">\K</span></span> | <span data-ttu-id="1e4d9-344">$0 시작 재설정(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-344">reset beginning of $0 (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-345">\N{name}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-345">\N{name}</span></span> | <span data-ttu-id="1e4d9-346">명명된 유니코드 문자(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-346">named Unicode character (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-347">\R</span><span class="sxs-lookup"><span data-stu-id="1e4d9-347">\R</span></span> | <span data-ttu-id="1e4d9-348">회선 중단(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-348">line break (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-349">\U...\E</span><span class="sxs-lookup"><span data-stu-id="1e4d9-349">\U...\E</span></span> | <span data-ttu-id="1e4d9-350">대문자 텍스트...(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-350">upper case text ... (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-351">\X</span><span class="sxs-lookup"><span data-stu-id="1e4d9-351">\X</span></span> | <span data-ttu-id="1e4d9-352">확장 유니코드 시퀀스(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-352">extended Unicode sequence (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-353">\%d123</span><span class="sxs-lookup"><span data-stu-id="1e4d9-353">\%d123</span></span> | <span data-ttu-id="1e4d9-354">10진수 문자 123(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-354">decimal character 123 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-355">\%xFF</span><span class="sxs-lookup"><span data-stu-id="1e4d9-355">\%xFF</span></span> | <span data-ttu-id="1e4d9-356">16진수 FF(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-356">hex character FF (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-357">\%o123원</span><span class="sxs-lookup"><span data-stu-id="1e4d9-357">\%o123</span></span> | <span data-ttu-id="1e4d9-358">8진수 문자 123(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-358">octal character 123 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-359">\%u1234</span><span class="sxs-lookup"><span data-stu-id="1e4d9-359">\%u1234</span></span> | <span data-ttu-id="1e4d9-360">유니코드 문자 0x1234(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-360">Unicode character 0x1234 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-361">\%U12345678</span><span class="sxs-lookup"><span data-stu-id="1e4d9-361">\%U12345678</span></span> | <span data-ttu-id="1e4d9-362">유니코드 문자 0x12345678(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-362">Unicode character 0x12345678 (NOT SUPPORTED) VIM</span></span> |

|  | <span data-ttu-id="1e4d9-363">문자 클래스 요소</span><span class="sxs-lookup"><span data-stu-id="1e4d9-363">Character class elements</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-364">x</span><span class="sxs-lookup"><span data-stu-id="1e4d9-364">x</span></span> | <span data-ttu-id="1e4d9-365">단일 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-365">single character</span></span> |
| <span data-ttu-id="1e4d9-366">A-Z</span><span class="sxs-lookup"><span data-stu-id="1e4d9-366">A-Z</span></span> | <span data-ttu-id="1e4d9-367">문자 범위(계속)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-367">character range (inclusive)</span></span> |
| <span data-ttu-id="1e4d9-368">\d</span><span class="sxs-lookup"><span data-stu-id="1e4d9-368">\d</span></span> | <span data-ttu-id="1e4d9-369">펄 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-369">Perl character class</span></span> |
| <span data-ttu-id="1e4d9-370">[:foo:]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-370">[:foo:]</span></span> | <span data-ttu-id="1e4d9-371">ASCII 문자 클래스 foo</span><span class="sxs-lookup"><span data-stu-id="1e4d9-371">ASCII character class foo</span></span> |
| <span data-ttu-id="1e4d9-372">\p{Foo}</span><span class="sxs-lookup"><span data-stu-id="1e4d9-372">\p{Foo}</span></span> | <span data-ttu-id="1e4d9-373">유니코드 문자 클래스 Foo</span><span class="sxs-lookup"><span data-stu-id="1e4d9-373">Unicode character class Foo</span></span> |
| <span data-ttu-id="1e4d9-374">\pF</span><span class="sxs-lookup"><span data-stu-id="1e4d9-374">\pF</span></span> | <span data-ttu-id="1e4d9-375">유니코드 문자 클래스 F(단일 문자 이름)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-375">Unicode character class F (one-letter name)</span></span> |

|  | <span data-ttu-id="1e4d9-376">문자 클래스 요소로 명명된 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-376">Named character classes as character class elements</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-377">[\d]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-377">[\d]</span></span> | <span data-ttu-id="1e4d9-378">숫자(≡ \d)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-378">digits (≡ \d)</span></span> |
| <span data-ttu-id="1e4d9-379">[^\d]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-379">[^\d]</span></span> | <span data-ttu-id="1e4d9-380">숫자 아님(≡ \D)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-380">not digits (≡ \D)</span></span> |
| <span data-ttu-id="1e4d9-381">[\D]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-381">[\D]</span></span> | <span data-ttu-id="1e4d9-382">숫자 아님(≡ \D)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-382">not digits (≡ \D)</span></span> |
| <span data-ttu-id="1e4d9-383">[^\D]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-383">[^\D]</span></span> | <span data-ttu-id="1e4d9-384">숫자 없음 아님(≡ \d)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-384">not not digits (≡ \d)</span></span> |
| <span data-ttu-id="1e4d9-385">[[:name:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-385">[[:name:]]</span></span> | <span data-ttu-id="1e4d9-386">문자 클래스 내 명명된 ASCII 클래스(문서 [:name:])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-386">named ASCII class inside character class (≡ [:name:])</span></span> |
| <span data-ttu-id="1e4d9-387">[^[:name:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-387">[^[:name:]]</span></span> | <span data-ttu-id="1e4d9-388">부정 문자 클래스 내의 명명된 ASCII 클래스(≡ [:^name:])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-388">named ASCII class inside negated character class (≡ [:^name:])</span></span> |
| <span data-ttu-id="1e4d9-389">[\p{Name}]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-389">[\p{Name}]</span></span> | <span data-ttu-id="1e4d9-390">문자 클래스 내의 명명된 유니코드 속성(≡ \p{Name})</span><span class="sxs-lookup"><span data-stu-id="1e4d9-390">named Unicode property inside character class (≡ \p{Name})</span></span> |
| <span data-ttu-id="1e4d9-391">[^\p{Name}]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-391">[^\p{Name}]</span></span> | <span data-ttu-id="1e4d9-392">부정된 문자 클래스 내의 명명된 유니코드 속성(≡ \P{Name})</span><span class="sxs-lookup"><span data-stu-id="1e4d9-392">named Unicode property inside negated character class (≡ \P{Name})</span></span> |

| <a name="user-content-perl"></a> | <span data-ttu-id="1e4d9-393">Perl 문자 클래스(모든 ASCII 전용)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-393">Perl character classes (all ASCII-only)</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-394">\d</span><span class="sxs-lookup"><span data-stu-id="1e4d9-394">\d</span></span> | <span data-ttu-id="1e4d9-395">숫자(≡ [0-9])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-395">digits (≡ [0-9])</span></span> |
| <span data-ttu-id="1e4d9-396">\D</span><span class="sxs-lookup"><span data-stu-id="1e4d9-396">\D</span></span> | <span data-ttu-id="1e4d9-397">숫자가 아님(≡ [^0-9])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-397">not digits (≡ [^0-9])</span></span> |
| <span data-ttu-id="1e4d9-398">\s</span><span class="sxs-lookup"><span data-stu-id="1e4d9-398">\s</span></span> | <span data-ttu-id="1e4d9-399">공백(≡ [\t\n\f\r])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-399">whitespace (≡ [\t\n\f\r])</span></span> |
| <span data-ttu-id="1e4d9-400">\S</span><span class="sxs-lookup"><span data-stu-id="1e4d9-400">\S</span></span> | <span data-ttu-id="1e4d9-401">공백이 아님(≡ [\t\n\f\r])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-401">not whitespace (≡ [^\t\n\f\r])</span></span> |
| <span data-ttu-id="1e4d9-402">\w</span><span class="sxs-lookup"><span data-stu-id="1e4d9-402">\w</span></span> | <span data-ttu-id="1e4d9-403">단어 문자(≡ [0-9A-Za-z\_])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-403">word characters (≡ [0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="1e4d9-404">\W</span><span class="sxs-lookup"><span data-stu-id="1e4d9-404">\W</span></span> | <span data-ttu-id="1e4d9-405">단어 문자가 아님(≡ [^0-9A-Za-z\_])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-405">not word characters (≡ [^0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="1e4d9-406">\h</span><span class="sxs-lookup"><span data-stu-id="1e4d9-406">\h</span></span> | <span data-ttu-id="1e4d9-407">수평 공간(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-407">horizontal space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-408">\H</span><span class="sxs-lookup"><span data-stu-id="1e4d9-408">\H</span></span> | <span data-ttu-id="1e4d9-409">수평 공간이 아님(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-409">not horizontal space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-410">\v</span><span class="sxs-lookup"><span data-stu-id="1e4d9-410">\v</span></span> | <span data-ttu-id="1e4d9-411">수직 공간(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-411">vertical space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-412">\V</span><span class="sxs-lookup"><span data-stu-id="1e4d9-412">\V</span></span> | <span data-ttu-id="1e4d9-413">수직 공간이 아님(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-413">not vertical space (NOT SUPPORTED)</span></span> |

|<a name="user-content-ascii"></a>  | <span data-ttu-id="1e4d9-414">ASCII 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-414">ASCII character classes</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-415">[[:alnum:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-415">[[:alnum:]]</span></span> | <span data-ttu-id="1e4d9-416">영숫자(≡ [0-9A-Za-z])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-416">alphanumeric (≡ [0-9A-Za-z])</span></span> |
| <span data-ttu-id="1e4d9-417">[[:alpha:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-417">[[:alpha:]]</span></span> | <span data-ttu-id="1e4d9-418">영문자(≡ [A-Za-z])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-418">alphabetic (≡ [A-Za-z])</span></span> |
| <span data-ttu-id="1e4d9-419">[[:ascii:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-419">[[:ascii:]]</span></span> | <span data-ttu-id="1e4d9-420">ASCII (≡ [\x00-\x7F])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-420">ASCII (≡ [\x00-\x7F])</span></span> |
| <span data-ttu-id="1e4d9-421">[[:blank:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-421">[[:blank:]]</span></span> | <span data-ttu-id="1e4d9-422">공백(≡ [\t])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-422">blank (≡ [\t])</span></span> |
| <span data-ttu-id="1e4d9-423">[[:cntrl:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-423">[[:cntrl:]]</span></span> | <span data-ttu-id="1e4d9-424">컨트롤(≡ [\x00-\x1F\x7F])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-424">control (≡ [\x00-\x1F\x7F])</span></span> |
| <span data-ttu-id="1e4d9-425">[[:digit:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-425">[[:digit:]]</span></span> | <span data-ttu-id="1e4d9-426">숫자(≡ [0-9])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-426">digits (≡ [0-9])</span></span> |
| <span data-ttu-id="1e4d9-427">[[:graph:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-427">[[:graph:]]</span></span> | <span data-ttu-id="1e4d9-428">그래픽(≡ `[!-~]` ≡ `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-428">graphical (≡ `[!-~]` ≡ `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`)</span></span> |
| <span data-ttu-id="1e4d9-429">[[:lower:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-429">[[:lower:]]</span></span> | <span data-ttu-id="1e4d9-430">소문자(≡ [a-z])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-430">lower case (≡ [a-z])</span></span> |
| <span data-ttu-id="1e4d9-431">[[:print:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-431">[[:print:]]</span></span> | <span data-ttu-id="1e4d9-432">인쇄 가능(≡ [-~] ≡ [[:graph:]])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-432">printable (≡ [-~] ≡ [[:graph:]])</span></span> |
| <span data-ttu-id="1e4d9-433">[[:punct:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-433">[[:punct:]]</span></span> | <span data-ttu-id="1e4d9-434">구두점(≡ [!-/:-@[-\`{-~])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-434">punctuation (≡ [!-/:-@[-\`{-~])</span></span> |
| <span data-ttu-id="1e4d9-435">[[:space:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-435">[[:space:]]</span></span> | <span data-ttu-id="1e4d9-436">흰 공백(≡ [\t\n\v\f\r])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-436">whitespace (≡ [\t\n\v\f\r])</span></span> |
| <span data-ttu-id="1e4d9-437">[[:upper:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-437">[[:upper:]]</span></span> | <span data-ttu-id="1e4d9-438">대문자(≡ [A-Z])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-438">upper case (≡ [A-Z])</span></span> |
| <span data-ttu-id="1e4d9-439">[[:word:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-439">[[:word:]]</span></span> | <span data-ttu-id="1e4d9-440">단어 문자(≡ [0-9A-Za-z\_])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-440">word characters (≡ [0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="1e4d9-441">[[:xdigit:]]</span><span class="sxs-lookup"><span data-stu-id="1e4d9-441">[[:xdigit:]]</span></span> | <span data-ttu-id="1e4d9-442">16진수(≡ [0-9A-Fa-f])</span><span class="sxs-lookup"><span data-stu-id="1e4d9-442">hex digit (≡ [0-9A-Fa-f])</span></span> |

| | <span data-ttu-id="1e4d9-443">유니코드 문자 클래스 이름--일반 카테고리</span><span class="sxs-lookup"><span data-stu-id="1e4d9-443">Unicode character class names--general category</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-444">C</span><span class="sxs-lookup"><span data-stu-id="1e4d9-444">C</span></span> | <span data-ttu-id="1e4d9-445">기타</span><span class="sxs-lookup"><span data-stu-id="1e4d9-445">other</span></span> |
| <span data-ttu-id="1e4d9-446">참조</span><span class="sxs-lookup"><span data-stu-id="1e4d9-446">Cc</span></span> | <span data-ttu-id="1e4d9-447">control</span><span class="sxs-lookup"><span data-stu-id="1e4d9-447">control</span></span> |
| <span data-ttu-id="1e4d9-448">Cf</span><span class="sxs-lookup"><span data-stu-id="1e4d9-448">Cf</span></span> | <span data-ttu-id="1e4d9-449">형식</span><span class="sxs-lookup"><span data-stu-id="1e4d9-449">format</span></span> |
| <span data-ttu-id="1e4d9-450">Cn</span><span class="sxs-lookup"><span data-stu-id="1e4d9-450">Cn</span></span> | <span data-ttu-id="1e4d9-451">할당되지 않은 코드 포인트(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-451">unassigned code points (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-452">Co</span><span class="sxs-lookup"><span data-stu-id="1e4d9-452">Co</span></span> | <span data-ttu-id="1e4d9-453">비공개 사용</span><span class="sxs-lookup"><span data-stu-id="1e4d9-453">private use</span></span> |
| <span data-ttu-id="1e4d9-454">Cs</span><span class="sxs-lookup"><span data-stu-id="1e4d9-454">Cs</span></span> | <span data-ttu-id="1e4d9-455">서로게이트</span><span class="sxs-lookup"><span data-stu-id="1e4d9-455">surrogate</span></span> |
| <span data-ttu-id="1e4d9-456">L</span><span class="sxs-lookup"><span data-stu-id="1e4d9-456">L</span></span> | <span data-ttu-id="1e4d9-457">글자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-457">letter</span></span> |
| <span data-ttu-id="1e4d9-458">LC</span><span class="sxs-lookup"><span data-stu-id="1e4d9-458">LC</span></span> | <span data-ttu-id="1e4d9-459">대/소문자(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-459">cased letter (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-460">L&amp;</span><span class="sxs-lookup"><span data-stu-id="1e4d9-460">L&amp;</span></span> | <span data-ttu-id="1e4d9-461">대/소문자(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-461">cased letter (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-462">Ll</span><span class="sxs-lookup"><span data-stu-id="1e4d9-462">Ll</span></span> | <span data-ttu-id="1e4d9-463">소문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-463">lowercase letter</span></span> |
| <span data-ttu-id="1e4d9-464">Lm</span><span class="sxs-lookup"><span data-stu-id="1e4d9-464">Lm</span></span> | <span data-ttu-id="1e4d9-465">수식어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-465">modifier letter</span></span> |
| <span data-ttu-id="1e4d9-466">Lo</span><span class="sxs-lookup"><span data-stu-id="1e4d9-466">Lo</span></span> | <span data-ttu-id="1e4d9-467">다른 편지</span><span class="sxs-lookup"><span data-stu-id="1e4d9-467">other letter</span></span> |
| <span data-ttu-id="1e4d9-468">LT</span><span class="sxs-lookup"><span data-stu-id="1e4d9-468">Lt</span></span> | <span data-ttu-id="1e4d9-469">제목 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-469">titlecase letter</span></span> |
| <span data-ttu-id="1e4d9-470">Lu</span><span class="sxs-lookup"><span data-stu-id="1e4d9-470">Lu</span></span> | <span data-ttu-id="1e4d9-471">대문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-471">uppercase letter</span></span> |
| <span data-ttu-id="1e4d9-472">M</span><span class="sxs-lookup"><span data-stu-id="1e4d9-472">M</span></span> | <span data-ttu-id="1e4d9-473">표시</span><span class="sxs-lookup"><span data-stu-id="1e4d9-473">mark</span></span> |
| <span data-ttu-id="1e4d9-474">Mc</span><span class="sxs-lookup"><span data-stu-id="1e4d9-474">Mc</span></span> | <span data-ttu-id="1e4d9-475">간격 표시</span><span class="sxs-lookup"><span data-stu-id="1e4d9-475">spacing mark</span></span> |
| <span data-ttu-id="1e4d9-476">Me</span><span class="sxs-lookup"><span data-stu-id="1e4d9-476">Me</span></span> | <span data-ttu-id="1e4d9-477">묶기 표시</span><span class="sxs-lookup"><span data-stu-id="1e4d9-477">enclosing mark</span></span> |
| <span data-ttu-id="1e4d9-478">Mn</span><span class="sxs-lookup"><span data-stu-id="1e4d9-478">Mn</span></span> | <span data-ttu-id="1e4d9-479">간격 없음 표시</span><span class="sxs-lookup"><span data-stu-id="1e4d9-479">non-spacing mark</span></span> |
| <span data-ttu-id="1e4d9-480">N</span><span class="sxs-lookup"><span data-stu-id="1e4d9-480">N</span></span> | <span data-ttu-id="1e4d9-481">숫자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-481">number</span></span> |
| <span data-ttu-id="1e4d9-482">Nd</span><span class="sxs-lookup"><span data-stu-id="1e4d9-482">Nd</span></span> | <span data-ttu-id="1e4d9-483">십진수</span><span class="sxs-lookup"><span data-stu-id="1e4d9-483">decimal number</span></span> |
| <span data-ttu-id="1e4d9-484">Nl</span><span class="sxs-lookup"><span data-stu-id="1e4d9-484">Nl</span></span> | <span data-ttu-id="1e4d9-485">문자 번호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-485">letter number</span></span> |
| <span data-ttu-id="1e4d9-486">아니오</span><span class="sxs-lookup"><span data-stu-id="1e4d9-486">No</span></span> | <span data-ttu-id="1e4d9-487">그 외 숫자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-487">other number</span></span> |
| <span data-ttu-id="1e4d9-488">P</span><span class="sxs-lookup"><span data-stu-id="1e4d9-488">P</span></span> | <span data-ttu-id="1e4d9-489">구두점</span><span class="sxs-lookup"><span data-stu-id="1e4d9-489">punctuation</span></span> |
| <span data-ttu-id="1e4d9-490">Pc</span><span class="sxs-lookup"><span data-stu-id="1e4d9-490">Pc</span></span> | <span data-ttu-id="1e4d9-491">커넥터 구두점</span><span class="sxs-lookup"><span data-stu-id="1e4d9-491">connector punctuation</span></span> |
| <span data-ttu-id="1e4d9-492">Pd</span><span class="sxs-lookup"><span data-stu-id="1e4d9-492">Pd</span></span> | <span data-ttu-id="1e4d9-493">대시 구두점</span><span class="sxs-lookup"><span data-stu-id="1e4d9-493">dash punctuation</span></span> |
| <span data-ttu-id="1e4d9-494">Pe</span><span class="sxs-lookup"><span data-stu-id="1e4d9-494">Pe</span></span> | <span data-ttu-id="1e4d9-495">구두점 닫기</span><span class="sxs-lookup"><span data-stu-id="1e4d9-495">close punctuation</span></span> |
| <span data-ttu-id="1e4d9-496">Pf</span><span class="sxs-lookup"><span data-stu-id="1e4d9-496">Pf</span></span> | <span data-ttu-id="1e4d9-497">최종 구두점</span><span class="sxs-lookup"><span data-stu-id="1e4d9-497">final punctuation</span></span> |
| <span data-ttu-id="1e4d9-498">Pi</span><span class="sxs-lookup"><span data-stu-id="1e4d9-498">Pi</span></span> | <span data-ttu-id="1e4d9-499">초기 구두점</span><span class="sxs-lookup"><span data-stu-id="1e4d9-499">initial punctuation</span></span> |
| <span data-ttu-id="1e4d9-500">Po</span><span class="sxs-lookup"><span data-stu-id="1e4d9-500">Po</span></span> | <span data-ttu-id="1e4d9-501">기타 구두점</span><span class="sxs-lookup"><span data-stu-id="1e4d9-501">other punctuation</span></span> |
| <span data-ttu-id="1e4d9-502">Ps</span><span class="sxs-lookup"><span data-stu-id="1e4d9-502">Ps</span></span> | <span data-ttu-id="1e4d9-503">구두점 열기</span><span class="sxs-lookup"><span data-stu-id="1e4d9-503">open punctuation</span></span> |
| <span data-ttu-id="1e4d9-504">S</span><span class="sxs-lookup"><span data-stu-id="1e4d9-504">S</span></span> | <span data-ttu-id="1e4d9-505">symbol</span><span class="sxs-lookup"><span data-stu-id="1e4d9-505">symbol</span></span> |
| <span data-ttu-id="1e4d9-506">Sc</span><span class="sxs-lookup"><span data-stu-id="1e4d9-506">Sc</span></span> | <span data-ttu-id="1e4d9-507">통화 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-507">currency symbol</span></span> |
| <span data-ttu-id="1e4d9-508">Sk</span><span class="sxs-lookup"><span data-stu-id="1e4d9-508">Sk</span></span> | <span data-ttu-id="1e4d9-509">수식어 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-509">modifier symbol</span></span> |
| <span data-ttu-id="1e4d9-510">Sm</span><span class="sxs-lookup"><span data-stu-id="1e4d9-510">Sm</span></span> | <span data-ttu-id="1e4d9-511">수학 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-511">math symbol</span></span> |
| <span data-ttu-id="1e4d9-512">So</span><span class="sxs-lookup"><span data-stu-id="1e4d9-512">So</span></span> | <span data-ttu-id="1e4d9-513">기타 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-513">other symbol</span></span> |
| <span data-ttu-id="1e4d9-514">Z</span><span class="sxs-lookup"><span data-stu-id="1e4d9-514">Z</span></span> | <span data-ttu-id="1e4d9-515">구분 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-515">separator</span></span> |
| <span data-ttu-id="1e4d9-516">Zl</span><span class="sxs-lookup"><span data-stu-id="1e4d9-516">Zl</span></span> | <span data-ttu-id="1e4d9-517">선 구분 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-517">line separator</span></span> |
| <span data-ttu-id="1e4d9-518">Zp</span><span class="sxs-lookup"><span data-stu-id="1e4d9-518">Zp</span></span> | <span data-ttu-id="1e4d9-519">단락 구분 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-519">paragraph separator</span></span> |
| <span data-ttu-id="1e4d9-520">Zs</span><span class="sxs-lookup"><span data-stu-id="1e4d9-520">Zs</span></span> | <span data-ttu-id="1e4d9-521">공간 구분 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-521">space separator</span></span> |

| <span data-ttu-id="1e4d9-522">유니코드 문자 클래스 이름--스크립트</span><span class="sxs-lookup"><span data-stu-id="1e4d9-522">Unicode character class names--scripts</span></span> |
| --- |
| <span data-ttu-id="1e4d9-523">아들람 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-523">Adlam</span></span> |
| <span data-ttu-id="1e4d9-524">아홈 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-524">Ahom</span></span> |
| <span data-ttu-id="1e4d9-525">아나톨리안\_상형문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-525">Anatolian\_Hieroglyphs</span></span> |
| <span data-ttu-id="1e4d9-526">아랍어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-526">Arabic</span></span> |
| <span data-ttu-id="1e4d9-527">아르메니아어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-527">Armenian</span></span> |
| <span data-ttu-id="1e4d9-528">아베스타 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-528">Avestan</span></span> |
| <span data-ttu-id="1e4d9-529">발리어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-529">Balinese</span></span> |
| <span data-ttu-id="1e4d9-530">바뭄 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-530">Bamum</span></span> |
| <span data-ttu-id="1e4d9-531">Bassa\_Vah</span><span class="sxs-lookup"><span data-stu-id="1e4d9-531">Bassa\_Vah</span></span> |
| <span data-ttu-id="1e4d9-532">바타크 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-532">Batak</span></span> |
| <span data-ttu-id="1e4d9-533">벵골어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-533">Bengali</span></span> |
| <span data-ttu-id="1e4d9-534">바이크슈키 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-534">Bhaiksuki</span></span> |
| <span data-ttu-id="1e4d9-535">보포모포 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-535">Bopomofo</span></span> |
| <span data-ttu-id="1e4d9-536">브라미 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-536">Brahmi</span></span> |
| <span data-ttu-id="1e4d9-537">점자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-537">Braille</span></span> |
| <span data-ttu-id="1e4d9-538">부기어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-538">Buginese</span></span> |
| <span data-ttu-id="1e4d9-539">부히드어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-539">Buhid</span></span> |
| <span data-ttu-id="1e4d9-540">캐나다인\_원주민</span><span class="sxs-lookup"><span data-stu-id="1e4d9-540">Canadian\_Aboriginal</span></span> |
| <span data-ttu-id="1e4d9-541">카리안</span><span class="sxs-lookup"><span data-stu-id="1e4d9-541">Carian</span></span> |
| <span data-ttu-id="1e4d9-542">백인\_알바니아어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-542">Caucasian\_Albanian</span></span> |
| <span data-ttu-id="1e4d9-543">차크마 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-543">Chakma</span></span> |
| <span data-ttu-id="1e4d9-544">Cham</span><span class="sxs-lookup"><span data-stu-id="1e4d9-544">Cham</span></span> |
| <span data-ttu-id="1e4d9-545">체로키어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-545">Cherokee</span></span> |
| <span data-ttu-id="1e4d9-546">초라스미안</span><span class="sxs-lookup"><span data-stu-id="1e4d9-546">Chorasmian</span></span> |
| <span data-ttu-id="1e4d9-547">일반</span><span class="sxs-lookup"><span data-stu-id="1e4d9-547">Common</span></span> |
| <span data-ttu-id="1e4d9-548">콥트어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-548">Coptic</span></span> |
| <span data-ttu-id="1e4d9-549">쿠네오페어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-549">Cuneiform</span></span> |
| <span data-ttu-id="1e4d9-550">키프로스어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-550">Cypriot</span></span> |
| <span data-ttu-id="1e4d9-551">키릴 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-551">Cyrillic</span></span> |
| <span data-ttu-id="1e4d9-552">데저렛 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-552">Deseret</span></span> |
| <span data-ttu-id="1e4d9-553">데바나가리어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-553">Devanagari</span></span> |
| <span data-ttu-id="1e4d9-554">디브스\_아쿠루</span><span class="sxs-lookup"><span data-stu-id="1e4d9-554">Dives\_Akuru</span></span> |
| <span data-ttu-id="1e4d9-555">도그라 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-555">Dogra</span></span> |
| <span data-ttu-id="1e4d9-556">듀플로이안 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-556">Duployan</span></span> |
| <span data-ttu-id="1e4d9-557">이집트\_상형문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-557">Egyptian\_Hieroglyphs</span></span> |
| <span data-ttu-id="1e4d9-558">엘바산 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-558">Elbasan</span></span> |
| <span data-ttu-id="1e4d9-559">엘리마어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-559">Elymaic</span></span> |
| <span data-ttu-id="1e4d9-560">에티오피아어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-560">Ethiopic</span></span> |
| <span data-ttu-id="1e4d9-561">그루지야어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-561">Georgian</span></span> |
| <span data-ttu-id="1e4d9-562">글라골어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-562">Glagolitic</span></span> |
| <span data-ttu-id="1e4d9-563">고딕어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-563">Gothic</span></span> |
| <span data-ttu-id="1e4d9-564">그란타 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-564">Grantha</span></span> |
| <span data-ttu-id="1e4d9-565">그리스어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-565">Greek</span></span> |
| <span data-ttu-id="1e4d9-566">구자라트어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-566">Gujarati</span></span> |
| <span data-ttu-id="1e4d9-567">Gunjala\_Gondi</span><span class="sxs-lookup"><span data-stu-id="1e4d9-567">Gunjala\_Gondi</span></span> |
| <span data-ttu-id="1e4d9-568">굴묵키어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-568">Gurmukhi</span></span> |
| <span data-ttu-id="1e4d9-569">간체</span><span class="sxs-lookup"><span data-stu-id="1e4d9-569">Han</span></span> |
| <span data-ttu-id="1e4d9-570">한글</span><span class="sxs-lookup"><span data-stu-id="1e4d9-570">Hangul</span></span> |
| <span data-ttu-id="1e4d9-571">하니피\_로힝야</span><span class="sxs-lookup"><span data-stu-id="1e4d9-571">Hanifi\_Rohingya</span></span> |
| <span data-ttu-id="1e4d9-572">하누누어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-572">Hanunoo</span></span> |
| <span data-ttu-id="1e4d9-573">해트란 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-573">Hatran</span></span> |
| <span data-ttu-id="1e4d9-574">히브리어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-574">Hebrew</span></span> |
| <span data-ttu-id="1e4d9-575">히라가나</span><span class="sxs-lookup"><span data-stu-id="1e4d9-575">Hiragana</span></span> |
| <span data-ttu-id="1e4d9-576">임페리얼\_아람어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-576">Imperial\_Aramaic</span></span> |
| <span data-ttu-id="1e4d9-577">상속됨</span><span class="sxs-lookup"><span data-stu-id="1e4d9-577">Inherited</span></span> |
| <span data-ttu-id="1e4d9-578">비문\_팔라비</span><span class="sxs-lookup"><span data-stu-id="1e4d9-578">Inscriptional\_Pahlavi</span></span> |
| <span data-ttu-id="1e4d9-579">비문\_파르티아누스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-579">Inscriptional\_Parthian</span></span> |
| <span data-ttu-id="1e4d9-580">자바어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-580">Javanese</span></span> |
| <span data-ttu-id="1e4d9-581">카이티 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-581">Kaithi</span></span> |
| <span data-ttu-id="1e4d9-582">칸나다어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-582">Kannada</span></span> |
| <span data-ttu-id="1e4d9-583">가타카나</span><span class="sxs-lookup"><span data-stu-id="1e4d9-583">Katakana</span></span> |
| <span data-ttu-id="1e4d9-584">카야\_리</span><span class="sxs-lookup"><span data-stu-id="1e4d9-584">Kayah\_Li</span></span> |
| <span data-ttu-id="1e4d9-585">하로쉬티</span><span class="sxs-lookup"><span data-stu-id="1e4d9-585">Kharoshthi</span></span> |
| <span data-ttu-id="1e4d9-586">키탄\_스몰\_스크립트</span><span class="sxs-lookup"><span data-stu-id="1e4d9-586">Khitan\_Small\_Script</span></span> |
| <span data-ttu-id="1e4d9-587">크메르어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-587">Khmer</span></span> |
| <span data-ttu-id="1e4d9-588">코지키</span><span class="sxs-lookup"><span data-stu-id="1e4d9-588">Khojki</span></span> |
| <span data-ttu-id="1e4d9-589">후다와디</span><span class="sxs-lookup"><span data-stu-id="1e4d9-589">Khudawadi</span></span> |
| <span data-ttu-id="1e4d9-590">라오스어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-590">Lao</span></span> |
| <span data-ttu-id="1e4d9-591">라틴어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-591">Latin</span></span> |
| <span data-ttu-id="1e4d9-592">렙차어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-592">Lepcha</span></span> |
| <span data-ttu-id="1e4d9-593">림부어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-593">Limbu</span></span> |
| <span data-ttu-id="1e4d9-594">선형\_A</span><span class="sxs-lookup"><span data-stu-id="1e4d9-594">Linear\_A</span></span> |
| <span data-ttu-id="1e4d9-595">선형\_B</span><span class="sxs-lookup"><span data-stu-id="1e4d9-595">Linear\_B</span></span> |
| <span data-ttu-id="1e4d9-596">리쑤 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-596">Lisu</span></span> |
| <span data-ttu-id="1e4d9-597">리키아 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-597">Lycian</span></span> |
| <span data-ttu-id="1e4d9-598">리디아 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-598">Lydian</span></span> |
| <span data-ttu-id="1e4d9-599">마하자니 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-599">Mahajani</span></span> |
| <span data-ttu-id="1e4d9-600">마카사르 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-600">Makasar</span></span> |
| <span data-ttu-id="1e4d9-601">말라얄람어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-601">Malayalam</span></span> |
| <span data-ttu-id="1e4d9-602">만다이아 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-602">Mandaic</span></span> |
| <span data-ttu-id="1e4d9-603">마니 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-603">Manichaean</span></span> |
| <span data-ttu-id="1e4d9-604">마르첸 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-604">Marchen</span></span> |
| <span data-ttu-id="1e4d9-605">Masaram\_Gondi</span><span class="sxs-lookup"><span data-stu-id="1e4d9-605">Masaram\_Gondi</span></span> |
| <span data-ttu-id="1e4d9-606">Medefaidrin</span><span class="sxs-lookup"><span data-stu-id="1e4d9-606">Medefaidrin</span></span> |
| <span data-ttu-id="1e4d9-607">Meetei\_Mayek</span><span class="sxs-lookup"><span data-stu-id="1e4d9-607">Meetei\_Mayek</span></span> |
| <span data-ttu-id="1e4d9-608">Mende\_Kikakui</span><span class="sxs-lookup"><span data-stu-id="1e4d9-608">Mende\_Kikakui</span></span> |
| <span data-ttu-id="1e4d9-609">메로이틱\_커시브</span><span class="sxs-lookup"><span data-stu-id="1e4d9-609">Meroitic\_Cursive</span></span> |
| <span data-ttu-id="1e4d9-610">메로이틱\_상형문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-610">Meroitic\_Hieroglyphs</span></span> |
| <span data-ttu-id="1e4d9-611">먀오 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-611">Miao</span></span> |
| <span data-ttu-id="1e4d9-612">모디</span><span class="sxs-lookup"><span data-stu-id="1e4d9-612">Modi</span></span> |
| <span data-ttu-id="1e4d9-613">몽골어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-613">Mongolian</span></span> |
| <span data-ttu-id="1e4d9-614">Mro</span><span class="sxs-lookup"><span data-stu-id="1e4d9-614">Mro</span></span> |
| <span data-ttu-id="1e4d9-615">Multani</span><span class="sxs-lookup"><span data-stu-id="1e4d9-615">Multani</span></span> |
| <span data-ttu-id="1e4d9-616">미얀마</span><span class="sxs-lookup"><span data-stu-id="1e4d9-616">Myanmar</span></span> |
| <span data-ttu-id="1e4d9-617">나바테안 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-617">Nabataean</span></span> |
| <span data-ttu-id="1e4d9-618">난디 나가리 기호</span><span class="sxs-lookup"><span data-stu-id="1e4d9-618">Nandinagari</span></span> |
| <span data-ttu-id="1e4d9-619">New\_Tai\_Lue</span><span class="sxs-lookup"><span data-stu-id="1e4d9-619">New\_Tai\_Lue</span></span> |
| <span data-ttu-id="1e4d9-620">뉴아</span><span class="sxs-lookup"><span data-stu-id="1e4d9-620">Newa</span></span> |
| <span data-ttu-id="1e4d9-621">은코어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-621">Nko</span></span> |
| <span data-ttu-id="1e4d9-622">Nushu</span><span class="sxs-lookup"><span data-stu-id="1e4d9-622">Nushu</span></span> |
| <span data-ttu-id="1e4d9-623">Nyiakeng\_Puachue\_Hmong</span><span class="sxs-lookup"><span data-stu-id="1e4d9-623">Nyiakeng\_Puachue\_Hmong</span></span> |
| <span data-ttu-id="1e4d9-624">Ogham</span><span class="sxs-lookup"><span data-stu-id="1e4d9-624">Ogham</span></span> |
| <span data-ttu-id="1e4d9-625">Ol\_Chiki</span><span class="sxs-lookup"><span data-stu-id="1e4d9-625">Ol\_Chiki</span></span> |
| <span data-ttu-id="1e4d9-626">고대\_헝가리어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-626">Old\_Hungarian</span></span> |
| <span data-ttu-id="1e4d9-627">고대\_이탈리아어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-627">Old\_Italic</span></span> |
| <span data-ttu-id="1e4d9-628">고대\_북\_아랍어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-628">Old\_North\_Arabian</span></span> |
| <span data-ttu-id="1e4d9-629">고대\_페름 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-629">Old\_Permic</span></span> |
| <span data-ttu-id="1e4d9-630">고대\_페르시아 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-630">Old\_Persian</span></span> |
| <span data-ttu-id="1e4d9-631">고대\_Sogdian</span><span class="sxs-lookup"><span data-stu-id="1e4d9-631">Old\_Sogdian</span></span> |
| <span data-ttu-id="1e4d9-632">고대\_남\_아랍어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-632">Old\_South\_Arabian</span></span> |
| <span data-ttu-id="1e4d9-633">고대\_터키어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-633">Old\_Turkic</span></span> |
| <span data-ttu-id="1e4d9-634">오리야어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-634">Oriya</span></span> |
| <span data-ttu-id="1e4d9-635">오사게</span><span class="sxs-lookup"><span data-stu-id="1e4d9-635">Osage</span></span> |
| <span data-ttu-id="1e4d9-636">오스만야</span><span class="sxs-lookup"><span data-stu-id="1e4d9-636">Osmanya</span></span> |
| <span data-ttu-id="1e4d9-637">Pahawh\_Hmong</span><span class="sxs-lookup"><span data-stu-id="1e4d9-637">Pahawh\_Hmong</span></span> |
| <span data-ttu-id="1e4d9-638">Palmyrene</span><span class="sxs-lookup"><span data-stu-id="1e4d9-638">Palmyrene</span></span> |
| <span data-ttu-id="1e4d9-639">Pau\_Cin\_Hau</span><span class="sxs-lookup"><span data-stu-id="1e4d9-639">Pau\_Cin\_Hau</span></span> |
| <span data-ttu-id="1e4d9-640">Phags\_Pa</span><span class="sxs-lookup"><span data-stu-id="1e4d9-640">Phags\_Pa</span></span> |
| <span data-ttu-id="1e4d9-641">페니키아 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-641">Phoenician</span></span> |
| <span data-ttu-id="1e4d9-642">Psalter\_Pahlavi</span><span class="sxs-lookup"><span data-stu-id="1e4d9-642">Psalter\_Pahlavi</span></span> |
| <span data-ttu-id="1e4d9-643">레장 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-643">Rejang</span></span> |
| <span data-ttu-id="1e4d9-644">룬어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-644">Runic</span></span> |
| <span data-ttu-id="1e4d9-645">사마리아 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-645">Samaritan</span></span> |
| <span data-ttu-id="1e4d9-646">사우라슈트라</span><span class="sxs-lookup"><span data-stu-id="1e4d9-646">Saurashtra</span></span> |
| <span data-ttu-id="1e4d9-647">Sharada</span><span class="sxs-lookup"><span data-stu-id="1e4d9-647">Sharada</span></span> |
| <span data-ttu-id="1e4d9-648">샤우 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-648">Shavian</span></span> |
| <span data-ttu-id="1e4d9-649">Siddham</span><span class="sxs-lookup"><span data-stu-id="1e4d9-649">Siddham</span></span> |
| <span data-ttu-id="1e4d9-650">수화 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-650">SignWriting</span></span> |
| <span data-ttu-id="1e4d9-651">싱할라어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-651">Sinhala</span></span> |
| <span data-ttu-id="1e4d9-652">Sogdian</span><span class="sxs-lookup"><span data-stu-id="1e4d9-652">Sogdian</span></span> |
| <span data-ttu-id="1e4d9-653">Sora\_Sompeng</span><span class="sxs-lookup"><span data-stu-id="1e4d9-653">Sora\_Sompeng</span></span> |
| <span data-ttu-id="1e4d9-654">Soyombo</span><span class="sxs-lookup"><span data-stu-id="1e4d9-654">Soyombo</span></span> |
| <span data-ttu-id="1e4d9-655">순다어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-655">Sundanese</span></span> |
| <span data-ttu-id="1e4d9-656">Syloti\_Nagri</span><span class="sxs-lookup"><span data-stu-id="1e4d9-656">Syloti\_Nagri</span></span> |
| <span data-ttu-id="1e4d9-657">시리아어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-657">Syriac</span></span> |
| <span data-ttu-id="1e4d9-658">타갈로그어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-658">Tagalog</span></span> |
| <span data-ttu-id="1e4d9-659">타그반와어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-659">Tagbanwa</span></span> |
| <span data-ttu-id="1e4d9-660">Tai\_Le</span><span class="sxs-lookup"><span data-stu-id="1e4d9-660">Tai\_Le</span></span> |
| <span data-ttu-id="1e4d9-661">Tai\_Tham</span><span class="sxs-lookup"><span data-stu-id="1e4d9-661">Tai\_Tham</span></span> |
| <span data-ttu-id="1e4d9-662">Tai\_Viet</span><span class="sxs-lookup"><span data-stu-id="1e4d9-662">Tai\_Viet</span></span> |
| <span data-ttu-id="1e4d9-663">Takri</span><span class="sxs-lookup"><span data-stu-id="1e4d9-663">Takri</span></span> |
| <span data-ttu-id="1e4d9-664">타밀어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-664">Tamil</span></span> |
| <span data-ttu-id="1e4d9-665">탕구트 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-665">Tangut</span></span> |
| <span data-ttu-id="1e4d9-666">텔루구어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-666">Telugu</span></span> |
| <span data-ttu-id="1e4d9-667">타아나 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-667">Thaana</span></span> |
| <span data-ttu-id="1e4d9-668">태국어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-668">Thai</span></span> |
| <span data-ttu-id="1e4d9-669">티베트어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-669">Tibetan</span></span> |
| <span data-ttu-id="1e4d9-670">티푸나구 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-670">Tifinagh</span></span> |
| <span data-ttu-id="1e4d9-671">티 루타 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-671">Tirhuta</span></span> |
| <span data-ttu-id="1e4d9-672">우가리아어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-672">Ugaritic</span></span> |
| <span data-ttu-id="1e4d9-673">바이</span><span class="sxs-lookup"><span data-stu-id="1e4d9-673">Vai</span></span> |
| <span data-ttu-id="1e4d9-674">완초 문자</span><span class="sxs-lookup"><span data-stu-id="1e4d9-674">Wancho</span></span> |
| <span data-ttu-id="1e4d9-675">Warang\_Citi</span><span class="sxs-lookup"><span data-stu-id="1e4d9-675">Warang\_Citi</span></span> |
| <span data-ttu-id="1e4d9-676">Yezidi</span><span class="sxs-lookup"><span data-stu-id="1e4d9-676">Yezidi</span></span> |
| <span data-ttu-id="1e4d9-677">이어</span><span class="sxs-lookup"><span data-stu-id="1e4d9-677">Yi</span></span> |
| <span data-ttu-id="1e4d9-678">Zanabazar\_Square</span><span class="sxs-lookup"><span data-stu-id="1e4d9-678">Zanabazar\_Square</span></span> |

|  | <span data-ttu-id="1e4d9-679">Vim 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-679">Vim character classes</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-680">\i</span><span class="sxs-lookup"><span data-stu-id="1e4d9-680">\i</span></span> | <span data-ttu-id="1e4d9-681">식별자 문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-681">identifier character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-682">\I</span><span class="sxs-lookup"><span data-stu-id="1e4d9-682">\I</span></span> | <span data-ttu-id="1e4d9-683">\i 제외 숫자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-683">\i except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-684">\k</span><span class="sxs-lookup"><span data-stu-id="1e4d9-684">\k</span></span> | <span data-ttu-id="1e4d9-685">키워드 문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-685">keyword character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-686">\K</span><span class="sxs-lookup"><span data-stu-id="1e4d9-686">\K</span></span> | <span data-ttu-id="1e4d9-687">숫자를 제외한 \k(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-687">\k except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-688">\f</span><span class="sxs-lookup"><span data-stu-id="1e4d9-688">\f</span></span> | <span data-ttu-id="1e4d9-689">파일 이름 문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-689">file name character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-690">\F</span><span class="sxs-lookup"><span data-stu-id="1e4d9-690">\F</span></span> | <span data-ttu-id="1e4d9-691">\f 숫자 제외(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-691">\f except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-692">\p</span><span class="sxs-lookup"><span data-stu-id="1e4d9-692">\p</span></span> | <span data-ttu-id="1e4d9-693">인쇄 가능한 문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-693">printable character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-694">\P</span><span class="sxs-lookup"><span data-stu-id="1e4d9-694">\P</span></span> | <span data-ttu-id="1e4d9-695">\p 숫자 제외(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-695">\p except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-696">\s</span><span class="sxs-lookup"><span data-stu-id="1e4d9-696">\s</span></span> | <span data-ttu-id="1e4d9-697">공백 문자([\t])(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-697">whitespace character (≡ [\t]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-698">\S</span><span class="sxs-lookup"><span data-stu-id="1e4d9-698">\S</span></span> | <span data-ttu-id="1e4d9-699">공백 문자가 아닌 문자([^ \t])(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-699">non-white space character (≡ [^ \t]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-700">\d</span><span class="sxs-lookup"><span data-stu-id="1e4d9-700">\d</span></span> | <span data-ttu-id="1e4d9-701">숫자(숫자 [0-9]) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-701">digits (≡ [0-9]) VIM</span></span> |
| <span data-ttu-id="1e4d9-702">\D</span><span class="sxs-lookup"><span data-stu-id="1e4d9-702">\D</span></span> | <span data-ttu-id="1e4d9-703">\d VIM이 아님</span><span class="sxs-lookup"><span data-stu-id="1e4d9-703">not \d VIM</span></span> |
| <span data-ttu-id="1e4d9-704">\x</span><span class="sxs-lookup"><span data-stu-id="1e4d9-704">\x</span></span> | <span data-ttu-id="1e4d9-705">16진수([0-9A-Fa-f])(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-705">hex digits (≡ [0-9A-Fa-f]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-706">\X</span><span class="sxs-lookup"><span data-stu-id="1e4d9-706">\X</span></span> | <span data-ttu-id="1e4d9-707">\x 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-707">not \x (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-708">\o</span><span class="sxs-lookup"><span data-stu-id="1e4d9-708">\o</span></span> | <span data-ttu-id="1e4d9-709">8진수([0-7])(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-709">octal digits (≡ [0-7]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-710">\O</span><span class="sxs-lookup"><span data-stu-id="1e4d9-710">\O</span></span> | <span data-ttu-id="1e4d9-711">\o(지원되지 않음) VIM 아님</span><span class="sxs-lookup"><span data-stu-id="1e4d9-711">not \o (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-712">\w</span><span class="sxs-lookup"><span data-stu-id="1e4d9-712">\w</span></span> | <span data-ttu-id="1e4d9-713">단어 문자 VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-713">word character VIM</span></span> |
| <span data-ttu-id="1e4d9-714">\W</span><span class="sxs-lookup"><span data-stu-id="1e4d9-714">\W</span></span> | <span data-ttu-id="1e4d9-715">not \w VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-715">not \w VIM</span></span> |
| <span data-ttu-id="1e4d9-716">\h</span><span class="sxs-lookup"><span data-stu-id="1e4d9-716">\h</span></span> | <span data-ttu-id="1e4d9-717">단어 문자(지원되지 않음) 헤드 VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-717">head of word character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-718">\H</span><span class="sxs-lookup"><span data-stu-id="1e4d9-718">\H</span></span> | <span data-ttu-id="1e4d9-719">\h(지원되지 않음) VIM 아님</span><span class="sxs-lookup"><span data-stu-id="1e4d9-719">not \h (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-720">\a</span><span class="sxs-lookup"><span data-stu-id="1e4d9-720">\a</span></span> | <span data-ttu-id="1e4d9-721">영문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-721">alphabetic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-722">\A</span><span class="sxs-lookup"><span data-stu-id="1e4d9-722">\A</span></span> | <span data-ttu-id="1e4d9-723">\a 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-723">not \a (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-724">\l</span><span class="sxs-lookup"><span data-stu-id="1e4d9-724">\l</span></span> | <span data-ttu-id="1e4d9-725">소문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-725">lowercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-726">\L</span><span class="sxs-lookup"><span data-stu-id="1e4d9-726">\L</span></span> | <span data-ttu-id="1e4d9-727">소문자 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-727">not lowercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-728">\u</span><span class="sxs-lookup"><span data-stu-id="1e4d9-728">\u</span></span> | <span data-ttu-id="1e4d9-729">대문자(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-729">uppercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-730">\U</span><span class="sxs-lookup"><span data-stu-id="1e4d9-730">\U</span></span> | <span data-ttu-id="1e4d9-731">대문자 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-731">not uppercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-732">\_x</span><span class="sxs-lookup"><span data-stu-id="1e4d9-732">\_x</span></span> | <span data-ttu-id="1e4d9-733">\x+줄 바꿈, 모든 x(지원되지 않음) VIM용</span><span class="sxs-lookup"><span data-stu-id="1e4d9-733">\x plus newline, for any x (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-734">\c</span><span class="sxs-lookup"><span data-stu-id="1e4d9-734">\c</span></span> | <span data-ttu-id="1e4d9-735">대/소문자 무시(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-735">ignore case (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-736">\C</span><span class="sxs-lookup"><span data-stu-id="1e4d9-736">\C</span></span> | <span data-ttu-id="1e4d9-737">대/소문자 일치(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-737">match case (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-738">\m</span><span class="sxs-lookup"><span data-stu-id="1e4d9-738">\m</span></span> | <span data-ttu-id="1e4d9-739">마법(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-739">magic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-740">\M</span><span class="sxs-lookup"><span data-stu-id="1e4d9-740">\M</span></span> | <span data-ttu-id="1e4d9-741">마법 아님(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-741">nomagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-742">\v</span><span class="sxs-lookup"><span data-stu-id="1e4d9-742">\v</span></span> | <span data-ttu-id="1e4d9-743">VIM(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-743">verymagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-744">\V</span><span class="sxs-lookup"><span data-stu-id="1e4d9-744">\V</span></span> | <span data-ttu-id="1e4d9-745">verynomagic(지원되지 않음) VIM</span><span class="sxs-lookup"><span data-stu-id="1e4d9-745">verynomagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1e4d9-746">\Z</span><span class="sxs-lookup"><span data-stu-id="1e4d9-746">\Z</span></span> | <span data-ttu-id="1e4d9-747">유니코드 조합 문자(지원되지 않음) VIM의 차이 무시</span><span class="sxs-lookup"><span data-stu-id="1e4d9-747">ignore differences in Unicode combining characters (NOT SUPPORTED) VIM</span></span> |

|  | <span data-ttu-id="1e4d9-748">매직</span><span class="sxs-lookup"><span data-stu-id="1e4d9-748">Magic</span></span> |
| --- | --- |
| <span data-ttu-id="1e4d9-749">(?{code})</span><span class="sxs-lookup"><span data-stu-id="1e4d9-749">(?{code})</span></span> | <span data-ttu-id="1e4d9-750">임의 Perl 코드(지원되지 않음) PERL</span><span class="sxs-lookup"><span data-stu-id="1e4d9-750">arbitrary Perl code (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="1e4d9-751">(?{code})</span><span class="sxs-lookup"><span data-stu-id="1e4d9-751">(??{code})</span></span> | <span data-ttu-id="1e4d9-752">지연된 임의 Perl 코드(지원되지 않음) PERL</span><span class="sxs-lookup"><span data-stu-id="1e4d9-752">postponed arbitrary Perl code (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="1e4d9-753">(?n)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-753">(?n)</span></span> | <span data-ttu-id="1e4d9-754">그룹 n을 캡처하기 위한 재귀 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-754">recursive call to regexp capturing group n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-755">(?+n)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-755">(?+n)</span></span> | <span data-ttu-id="1e4d9-756">상대 그룹에 대한 재귀 호출 +n(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-756">recursive call to relative group +n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-757">(?-n)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-757">(?-n)</span></span> | <span data-ttu-id="1e4d9-758">상대 그룹에 대한 재귀 호출 -n(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-758">recursive call to relative group -n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-759">(?C)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-759">(?C)</span></span> | <span data-ttu-id="1e4d9-760">PCRE 콜아웃(지원되지 않음) PCRE</span><span class="sxs-lookup"><span data-stu-id="1e4d9-760">PCRE callout (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="1e4d9-761">(?R)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-761">(?R)</span></span> | <span data-ttu-id="1e4d9-762">전체 regexp(?0)에 대한 재귀 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-762">recursive call to entire regexp (≡ (?0)) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-763">(?&amp;name)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-763">(?&amp;name)</span></span> | <span data-ttu-id="1e4d9-764">명명된 그룹에 대한 재귀 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-764">recursive call to named group (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-765">(?P=이름)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-765">(?P=name)</span></span> | <span data-ttu-id="1e4d9-766">명명된 역참조(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-766">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-767">(?P&gt;name)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-767">(?P&gt;name)</span></span> | <span data-ttu-id="1e4d9-768">명명된 그룹에 대한 재귀 호출(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-768">recursive call to named group (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-769">(?(조건)true</span><span class="sxs-lookup"><span data-stu-id="1e4d9-769">(?(cond)true</span></span>|<span data-ttu-id="1e4d9-770">false)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-770">false)</span></span> | <span data-ttu-id="1e4d9-771">조건부 분기(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-771">conditional branch (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-772">(?(조건)true)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-772">(?(cond)true)</span></span> | <span data-ttu-id="1e4d9-773">조건부 분기(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-773">conditional branch (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-774">(\*ACCEPT)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-774">(\*ACCEPT)</span></span> | <span data-ttu-id="1e4d9-775">regexps를 Prolog와 유사하게 만들기(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-775">make regexps more like Prolog (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-776">(\*COMMIT)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-776">(\*COMMIT)</span></span> | <span data-ttu-id="1e4d9-777">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-777">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-778">(\*F)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-778">(\*F)</span></span> | <span data-ttu-id="1e4d9-779">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-779">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-780">(\*FAIL)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-780">(\*FAIL)</span></span> | <span data-ttu-id="1e4d9-781">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-781">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-782">(\*MARK)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-782">(\*MARK)</span></span> | <span data-ttu-id="1e4d9-783">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-783">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-784">(\*PRUNE)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-784">(\*PRUNE)</span></span> | <span data-ttu-id="1e4d9-785">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-785">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-786">(\*SKIP)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-786">(\*SKIP)</span></span> | <span data-ttu-id="1e4d9-787">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-787">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-788">(\*THEN)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-788">(\*THEN)</span></span> | <span data-ttu-id="1e4d9-789">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-789">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-790">(\*Any)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-790">(\*ANY)</span></span> | <span data-ttu-id="1e4d9-791">줄바꿈 규칙 설정 (지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-791">set newline convention (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-792">(\*AnyCRLF)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-792">(\*ANYCRLF)</span></span> | <span data-ttu-id="1e4d9-793">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-793">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-794">(\*CR)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-794">(\*CR)</span></span> | <span data-ttu-id="1e4d9-795">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-795">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-796">(\*CRLF)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-796">(\*CRLF)</span></span> | <span data-ttu-id="1e4d9-797">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-797">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-798">(\*LF)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-798">(\*LF)</span></span> | <span data-ttu-id="1e4d9-799">(지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-799">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1e4d9-800">(\*BSR\_ANYCRLF)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-800">(\*BSR\_ANYCRLF)</span></span> | <span data-ttu-id="1e4d9-801">\R 컨벤션(지원되지 않음) PCRE 설정</span><span class="sxs-lookup"><span data-stu-id="1e4d9-801">set \R convention (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="1e4d9-802">(\*BSR\_UNICODE)</span><span class="sxs-lookup"><span data-stu-id="1e4d9-802">(\*BSR\_UNICODE)</span></span> | <span data-ttu-id="1e4d9-803">(지원되지 않음) PCRE</span><span class="sxs-lookup"><span data-stu-id="1e4d9-803">(NOT SUPPORTED) PCRE</span></span> |

## <span data-ttu-id="1e4d9-804">콘텐츠 라이선스</span><span class="sxs-lookup"><span data-stu-id="1e4d9-804">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="1e4d9-805">이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-805">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="1e4d9-806">원래 페이지는 [여기](https://github.com/google/re2/wiki/Syntax)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-806">The original page can be found [here](https://github.com/google/re2/wiki/Syntax).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="1e4d9-807">이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e4d9-807">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="1e4d9-808">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e4d9-808">See also</span></span>

- [<span data-ttu-id="1e4d9-809">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="1e4d9-809">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)