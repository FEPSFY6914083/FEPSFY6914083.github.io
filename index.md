# Galois Theory and the Limit of Algebra

## Table of Contents
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Why the Early Formulas Worked](#why-the-early-formulas-worked)
- [The Abel–Ruffini Theorem](#the-abel–ruffini-theorem)
- [Permutations of Roots](#permutations-of-roots)
- [Solvable Groups and Why They Matter](#solvable-groups-and-why-they-matter)
- [The Group Structure Behind the Quintic Barrier](#the-group-structure-behind-the-quintic-barrier)
- [Conclusion](#conclusion)
- [References](#references)

---

## Abstract
For centuries mathematicians searched for general formulas that could solve polynomial equations. Methods for quadratics, cubics and quartics all succeeded by reducing the equations to expressions involving roots. These early successes led to the expectation that a similar method should exist for the quintic. Abel proved this was impossible, and Galois later explained why by showing that solvability depends on the structure of the permutations of the roots. When these permutations can be broken into simple layers, as in lower-degree equations, a formula can be built. The quintic fails because its permutation group, \(S_5\), has no such structure. Its internal organisation prevents any sequence of algebraic steps from matching the behaviour of its roots. This article explores the ideas behind this barrier and shows how Galois theory provides a structural explanation for the failure of a quintic formula.

---

<div id="Introduction_InText">

## Introduction
The pursuit for general methods to solve polynomial equations has been a key component of mathematics for centuries. The quadratic formula, which may come across as trivial today, represented major progress for mathematicians such as al-Khwarizmi, and later work by Cardano and others in the sixteenth century produced general formulas for cubic and quartic equations (Burton, 2011). This common trend suggested that higher-degree equations should follow the same pattern. If degrees two, three and four had closed-form solutions, it seemed natural to assume a similar method for the fifth degree. Yet every attempt to extend existing techniques failed. As Bruns (2020) observes, this history shows “why formulae exist for equations of degree four or less … and why they do not for degree five or more”.

This shift in algebra was that familiar methods were no longer the right tool to solve higher order polynomials. Progress required focusing on the structure of the roots rather than manipulating the equation directly. This leads to the central idea behind Galois theory: the way the roots of a polynomial can be rearranged, while still preserving algebraic relationships, determines whether a formula using radicals can exist (Stewart, 2015). To see why the fifth-degree case behaves differently, it helps to first understand why the earlier formulas were possible.

</div>
<div id="Analysis_InText">

---

## Why the Early Formulas Worked
Early mathematicians could explain the earlier successes, but the same approach failed once they moved to the fifth degree. With quadratics, completing the square lets you isolate the root in a straightforward way. For cubic and quartic equations, the methods developed by del Ferro, Tartaglia and Cardano turned the problems into forms where the roots could still be written using basic operations and familiar root expressions. The links between the roots stayed simple enough to handle. Even when the working became longer, you could still reach the roots using addition, subtraction, multiplication, division and square or cube roots. This level of structure is what made general formulas possible for degrees two to four.

---

## The Abel–Ruffini Theorem
The difficulty with the fifth degree comes from the way the roots of a quintic polynomial relate to one another. For lower degrees, each method relies on reducing the equation to a simpler form that eventually leads to square or cube roots. This reduction works because the relationships between the roots can be controlled and expressed through those operations. With quintic polynomials, this reduction step breaks down. Approaches such as trying to remove certain terms or constructing auxiliary equations no longer produce expressions that depend only on roots of simpler polynomials. The connections between the five roots become too intricate to be captured through repeated use of square or cube roots. Abel proved this by showing that no sequence of algebraic steps can rearrange a general quintic into a form where the roots can be written using a finite combination of arithmetic operations and root extractions (Stillwell, 2010). This explained why earlier attempts failed and showed that the obstacle was rooted in fifth-degree polynomials rather than in the methods used.

---

## Permutations of Roots

### Table 1. Number of root permutations by degree

| Degree | Permutations | Group | Structure |
|--------|--------------|--------|-----------|
| 2 | 2 | \(S_2\) | Simple swap |
| 3 | 6 | \(S_3\) | Breaks into subgroups |
| 4 | 24 | \(S_4\) | Still structured |
| 5 | 120 | \(S_5\) | No solvable chain |

<div id="perm-chart" style="width:100%;max-width:600px;height:350px;margin-top:10px;"></div>

<script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
<script>
// Load Google Charts and the corechart package
if (window.google && window.google.charts) {
  google.charts.load('current', { packages: ['corechart'] });
  google.charts.setOnLoadCallback(drawPermChart);
}

// Draw a column chart for permutations by degree
function drawPermChart() {
  var data = google.visualization.arrayToDataTable([
    ['Degree', 'Permutations'],
    ['2', 2],
    ['3', 6],
    ['4', 24],
    ['5', 120]
  ]);

  var options = {
    title: 'Number of permutations by degree',
    legend: { position: 'none' },
    hAxis: { title: 'Degree' },
    vAxis: { title: 'Permutations' }
  };

  var chart = new google.visualization.ColumnChart(
    document.getElementById('perm-chart')
  );
  chart.draw(data, options);
}
</script>

A permutation is simply a way of reordering the roots of a polynomial while keeping track of which root moves to which position. Even a basic quadratic shows how this works. A quadratic has two roots; you can list them as \([r_1, r_2]\), so there are only two possible arrangements. Both lists contain the same numbers, and the equation keeps all its algebraic relationships. As the degree increases, the number of possible rearrangements grows sharply, as shown in Table 1. Thinking of root behaviour in this way reveals that each polynomial comes with its own set of allowable permutations, and understanding this set forms the starting point of Galois’s approach.

---

## Solvable Groups and Why They Matter
The cubic is a good place to see how Galois’s ideas connect to an actual formula. A cubic has three roots, and the six ways to rearrange them form a group that contains a few smaller, simpler patterns. Some of these rearrangements just cycle the roots, and others swap two of them. These smaller patterns sit inside the full group in a way that mirrors how the cubic formula is built. When you solve a cubic, you first form a square-root expression and then use that result inside a cube root. Each step depends on the one before it, and this matches the ordered structure inside its permutation group. This is what Galois meant by a solvable group: the symmetries can be broken into stages that line up with the steps in a root-based formula (Stewart, 2015).

---

## The Group Structure Behind the Quintic Barrier
The difficulty with the quintic comes from how its root permutations organise themselves. The five roots can be rearranged in one hundred and twenty different ways, and the group formed by these permutations, called \(S_5\), contains all of them. The key issue is that the permutations in \(S_5\) cannot be arranged into a chain of smaller subgroups that naturally follow one another. In group theory terms, there is no sequence of subgroups where each one is normal in the next, and where the quotients are simple enough to match the operations used in root-based formulas. In \(S_5\), the first non-trivial normal subgroup is the alternating group \(A_5\), and \(A_5\) is simple, which means it cannot be broken down any further. Because this structure stops at \(A_5\), there is no step-by-step path through the group that matches the layers needed to build an expression from square or cube roots. This is why no general formula for the quintic can exist.

</div>

---

## Conclusion
The search for general formulas for polynomial equations followed a clear pattern in the lower degrees, where the structure of the roots allowed the equations to be reduced in stages. This pattern breaks at the quintic. Abel showed that no sequence of algebraic steps can reshape a general fifth-degree equation into a form built from simple root expressions. Galois explained why, by linking solvability to the structure of the permutations of the roots. The group \(S_5\) has no layers that match the steps of a root-based formula, which is why the quintic has no general solution.

<hr>

<!-- Last modified time from GitHub -->
<div id="last-updated">Loading last modified time...</div>
<button onclick="verifyLastUpdatedTime()" style="display:block;margin:10px 0;padding:6px 12px;">
  Verify Last Modified Time
</button>

<!-- Total word count for sections Introduction + main discussion -->
<p id="totalWordCount"></p>

<script>
// ///////////////// Last modified time using GitHub API ///////////////////

async function getLastUpdatedTime() {
  const username = 'FEPSFY6914083';
  const repo = 'FEPSFY6914083.github.io';

  const url = `https://api.github.com/repos/${username}/${repo}/commits`;
  try {
    const response = await fetch(url, {
      method: 'GET',
      headers: {
        'Accept': 'application/vnd.github.v3+json'
      }
    });

    if (!response.ok) {
      throw new Error('Error fetching data: ' + response.status + ' - ' + response.statusText);
    }

    const commits = await response.json();
    if (commits && commits.length > 0) {
      const lastCommitDate = new Date(commits[0].commit.committer.date);
      document.getElementById('last-updated').innerText =
        'Last Modified Time: ' + lastCommitDate.toLocaleString('en-GB');
    } else {
      document.getElementById('last-updated').innerText =
        'No commits found in the repository.';
    }
  } catch (error) {
    console.error('Error fetching the last updated time:', error);
    document.getElementById('last-updated').innerText =
      'Error fetching update time. Please check the repository details.';
  }
}

// Called when the button is pressed
async function verifyLastUpdatedTime() {
  document.getElementById('last-updated').innerText = 'Verifying...';
  await getLastUpdatedTime();
  alert('Last modified time has been successfully verified from GitHub API.');
}

// ///////////////// Word count for Introduction + Analysis ///////////////////

// Get word count for a section with a given id
function getSectionWordCount(sectionId) {
  const element = document.getElementById(sectionId);
  if (!element) return 0;

  const text = element.textContent.trim();
  if (text === '') return 0;

  const words = text.split(/\s+/);
  return words.length;
}

// Compute and display total word count
function displayTotalWordCount() {
  const introCount = getSectionWordCount('Introduction_InText');
  const analysisCount = getSectionWordCount('Analysis_InText');
  const total = introCount + analysisCount;

  const p = document.getElementById('totalWordCount');
  if (p) {
    p.innerText = 'Total word count (Introduction + main discussion): ' + total;
  }
}

// Run both features when the page loads
window.onload = function () {
  getLastUpdatedTime();
  displayTotalWordCount();
};
</script>

---

## References
Bruns, P. (2020) ‘Why there is no formula for the quintic’, *The Mathematics Enthusiast*, 17(1), pp. 23–40.  
Burton, D. (2011) *The History of Mathematics*. 7th edn. New York: McGraw-Hill.  
Stewart, I. (2015) *Galois Theory*. 4th edn. Boca Raton: CRC Press.  
Stillwell, J. (2010) *Mathematics and Its History*. 3rd edn. New York: Springer.
