---
layout: page
title: WINC
description: A chromosome-painting-based pipeline to infer local ancestry under limited source availability
img: assets/img/SummaryWINC.jpg
importance: 2
category: work
related_publications: molinaro2021chromosome
---

Supervised by Dr. Montinaro (University of Bari + University of Tartu) & Prof. Pagani (University of Padua + University of Tartu)

<b>Why is this project cool?</b> 
<html>
<head>
    <style>
        .highlight {
            border: 2px solid gray;
            padding: 5px;
            margin-bottom: 20px;
            display: inline-block; /* Adjust display property as per your layout requirements */
        }
    </style>
</head>
<body>

<div id="jsonParagraph"></div>

<script>
    const data = {
        "paragraph": "Guess what? We've just whipped up WINC: a new tool for local ancestry deconvolution (LAI). It's like a genetic compass that tells us exactly where the roots of a mixed bunch of folks are, giving us major insights into how different communities came to be. The best part? Our method cracks a tough nut that other tools grapple with: they always demand heaps of samples from each proxy source. But not ours! With WINC pipeline, just a duo of samples from each source does the trick. This means we can dive into studying all kinds of critters and creatures, unlocking a whole universe of possibilities!"
    };

    const div = document.getElementById("jsonParagraph");
    const span = document.createElement("span");
    span.textContent = data.paragraph;
    span.classList.add("highlight");
    div.appendChild(span);
</script>

</body>
</html>

Contemporary individuals are the combination of genetic fragments inherited from ancestors belonging to multiple populations, as
the result of migration and admixture. Isolating and characterizing these layers are crucial to the understanding of the genetic history
of a given population. Ancestry deconvolution approaches make use of a large amount of source individuals, therefore constraining
the performance of Local Ancestry Inferences when only few genomes are available from a given population. Here we present WINC,
a local ancestry framework derived from the combination of ChromoPainter and NNLS approaches, as a method to retrieve local
genetic assignments when only a few reference individuals are available. The framework is aided by a score assignment based on
source differentiation to maximize the amount of sequences retrieved and is capable of retrieving accurate ancestry assignments
when only two individuals for source populations are used.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/SummaryWINC.jpg" title="WINC Summary" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Schematic representation of WINC approach. WINC is based on the ChromoPainter/NNLS framework, with the additional step of splitting the copying vectors resulting from the ChromoPainter (CP) run before analyzing them through the NNLS step. First step: ChromoPainter run. CP identifies the closest neighbor “donor” for any “recipient” individual haplotype. ChromoPainter then reconstructs the recipient individuals as a combination of genomic segments, or chunks, “donated” by any other individual in the data set. The information is then stored in copying vectors, where, for each recipient haplotype, it is indicated which donor individual is the closest neighbour. In this way, we obtain the copying vectors of our target populations: both the sources and the admixed individuals. Second step: splitting copying vectors. We then split the copying vectors in genomic windows of the same length. Window size depends on the ancestry chunks, which in turn depends on the amount of generations since the admixture. Third step: performing NNLS analyses on the copying vector’s genomic windows obtained from the previous step. The NNLS step assigns a window to a specific ancestry, by reconstructing the painting profile of a given individual as a combination (or proportion) of copying vectors from the source individuals.
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/SimulationWINC.png" title="Simulated samples and FST between simulated groups" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   Simulated samples and FST between simulated groups 
</div>
