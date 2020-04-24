### Genomics Sequence Utilities

_The code for these tools are unpublished, primarily because they
involved too many BMS-internal connections to cleanly extract it for
disclosure. This is a stub repo to just host a few (disclosure
approved) screenshots._

### Align This

Our researchers were generally happy to run their own alignments, but
didn't have tools at their disposal to do so. Align This presents a
simple-to-use web front end that allowed two or more sequences to be
provided, either as accessions or raw Fasta format. Multiple alignment
algorithms could be chosen, and power users could specify command line
flags. Default output was colorized HTML, with several color schemes
available that could be dynamically selected after alignment. The
default scheme, "Entropy Gaps", is a custom visualization that
highlights "high entropy" columns in the alignment, as well as gaps.

![Align This Results][AlignThis]

Align This also had a special mode where a second set of "reference"
sequences could be provided. Each of the "query" sequences were
aligned individually, pair-wise, to each of the references. Each query
was then "assigned" to the "best" reference, with results typcially
being presented in an Excel workbook. This was popular with our
virologists, who could combine their experimental sequences with
multiple viral reference strains, letting Align This pick the most
likely source strain for each of their sequences.

AlignThis functionality is also available as a Perl API.

### Genomic Sim4

Our cloning group was industry-leading, but unexpected differences
would still be found in our clones. The question was then: Are these
differences due to a PCR artifact, or do they represent known
polymorphisms? Genomic Sim4 was designed to allow clone sequences to
be compared in the context of a reference genome, with polymorphisms
from dbSNP and Thousand Genomes superimposed.

![Genomic Sim4 Results][GenomicSim4]

The analysis also showed intronic splice junctions extracted from the
genome, along with expected base frequency at each of the 5 (10?)
flanking positions.

### Friendly Blast

We maintained a large collection of blast databases, comprising
internal, public and vendor-supplied sequences. These databases had
varying "refresh" schedules, which resulted in disapointment when
queries were run on stale data. Friendly Blast was initially put in
place to help centralize our DBs, as well as to clearly indicate the
age of each database.

The system evolved to allow simple query submission (file upload,
accession list, raw fasta), automated algorithm selection and the
availability of multiple output formats, including popular "colorized
raw" and Excel workbook reports.

The system would also function as a web service, and supported TSV,
XML and JSON result formats.

FriendlyBlast was later extended to include support for
[IgBlast][IgBlast], including another "colorized raw" format and an
Excel report. These searches were popular with colleagues designing
our antibody-based therapies.

_I managed to leave BMS without a screenshot for Friendly Blast ..._

* [BMS Public Disclosure approval](PubD-Disclosure-Approval.md)

[AlignThis]: img/AlignThis.png
[GenomicSim4]: img/GenomicSim4.png
[IgBlast]: https://www.ncbi.nlm.nih.gov/igblast/
