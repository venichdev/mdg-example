# References Management

This folder contains your bibliography and reference management files.

---

## Reference Management Strategy

### 1. Use a Reference Manager

**Recommended: Zotero (Free & Open Source)**
- Download: https://www.zotero.org/
- Browser connector for easy paper import
- Automatic citation formatting
- Cloud sync across devices
- Export to BibTeX for LaTeX

**Alternative: Mendeley**
- Download: https://www.mendeley.com/
- Good for PDF annotation
- Social features for discovering papers

### 2. Organization

#### Collections/Folders
Create collections by topic:
```
My Library/
├── Torque Vectoring/
│   ├── Fundamentals
│   ├── Energy Optimization
│   └── Recent Methods (2020+)
├── Electric Vehicles/
│   ├── Multi-Motor Systems
│   ├── Battery & Energy
│   └── Vehicle Dynamics
├── Autonomous Vehicles/
│   ├── Control Architectures
│   └── ADAS Integration
├── Control Methods/
│   ├── MPC
│   ├── Optimal Control
│   └── Other Methods
└── Experimental Validation/
    ├── Simulation Tools
    └── Real Vehicle Tests
```

#### Tags
Use tags for cross-cutting themes:
- methodology-type (simulation, experimental, analytical)
- highly-relevant
- review-paper
- to-read
- read
- cited-in-thesis
- baseline-comparison

---

## Citation Style

### For Naresuan University
**Check your department requirements!**

Common styles for engineering:
- **IEEE** (most common for electrical/mechanical engineering)
- **APA** (if specified)
- **Chicago** (less common for engineering)

### IEEE Citation Examples

**Journal Article:**
[1] A. Author, B. Author, and C. Author, "Title of paper," *Abbrev. Journal Name*, vol. X, no. Y, pp. start-end, Month Year.

**Conference Paper:**
[2] A. Author and B. Author, "Title of paper," in *Proc. Conference Name*, City, Country, Year, pp. start-end.

**Book:**
[3] A. Author, *Title of Book*, Edition. City, Country: Publisher, Year.

**Thesis:**
[4] A. Author, "Title of thesis," M.S. thesis, Dept. Abbrev., Univ. Name, City, Country, Year.

**Online Source:**
[5] Author. "Title." Website Name. URL (accessed Month Day, Year).

---

## Files to Keep Here

### 1. BibTeX File (if using LaTeX)
`thesis_references.bib`
- Export from your reference manager
- Keep it updated
- Version control this file

### 2. Citation Key Convention
Use consistent citation keys:
```
AuthorLastNameYearKeyword

Examples:
- Smith2023TorqueVectoring
- Zhang2022EnergyOptimization
- Johnson2021AutonomousEV
```

### 3. Annotated Bibliography (Optional but Helpful)
`annotated_bibliography.md`

For each important paper, note:
- Key contribution
- Methodology used
- Main results
- Relevance to your work
- Strengths and limitations

---

## Citation Checklist

### Quality Indicators
- [ ] Peer-reviewed sources (journals, conferences)
- [ ] Recent references (majority from last 5 years)
- [ ] Seminal/foundational works included
- [ ] Appropriate balance of breadth and depth
- [ ] Authoritative sources (top journals/conferences)

### Coverage
- [ ] Theoretical background adequately cited
- [ ] State-of-the-art comprehensively covered
- [ ] All claims are supported by citations
- [ ] Comparison baseline methods are cited
- [ ] Methodology references included

### Citation Ethics
- [ ] All sources properly attributed
- [ ] No plagiarism (paraphrase + cite)
- [ ] Direct quotes are clearly marked
- [ ] Self-citations are appropriate and necessary
- [ ] All cited works have been read (at minimum abstract + conclusions)

---

## Reference Count Guidelines

**For Master's Thesis:**
- Typical: 50-100 references
- Minimum: ~40 (for focused topic)
- Maximum: ~150 (for comprehensive coverage)

**Distribution:**
- Fundamentals/Background: 20-30%
- State-of-the-Art: 40-50%
- Methods/Tools: 15-25%
- Validation/Comparison: 10-20%

**Recency:**
- Within last 5 years: ~60-70%
- 5-10 years old: ~20-30%
- Older (seminal works): ~10-15%

---

## Tools for Finding Papers

### Academic Databases
1. **IEEE Xplore** - Engineering papers
2. **Google Scholar** - Broad search
3. **Web of Science** - Citation tracking
4. **Scopus** - Comprehensive indexing
5. **ScienceDirect** - Elsevier journals
6. **SpringerLink** - Springer journals
7. **arXiv** - Preprints

### Discovery Tools
1. **Connected Papers** - Visualize paper relationships
   - https://www.connectedpapers.com/
2. **Research Rabbit** - Citation tracking and recommendations
3. **Semantic Scholar** - AI-powered search
4. **Litmaps** - Literature mapping

### Search Strategies
- Use Boolean operators: AND, OR, NOT
- Use quotation marks for exact phrases: "torque vectoring"
- Use wildcards: vehic* (matches vehicle, vehicles)
- Filter by year (focus on recent)
- Sort by citations (for established work)
- Check "Cited by" to find recent work

---

## Citation While Writing

### In-Text Citations

**IEEE Style:**
- Statement supported by one source [1].
- Statement supported by multiple sources [1], [2].
- Statement supported by range [1]-[5].
- Author mentioned: According to Smith [1], ...

**APA Style (if required):**
- (Author, Year)
- (Author1 & Author2, Year)
- (Author1 et al., Year) for 3+ authors

### When to Cite
✓ Others' ideas, theories, or opinions
✓ Facts not commonly known
✓ Statistics and data
✓ Direct quotations
✓ Paraphrased material
✓ Figures or tables adapted from sources

✗ Your own original ideas
✗ Common knowledge in the field
✗ Your own experimental data/results

### Common Citation Mistakes
- ❌ Citing papers you haven't read (cite the original)
- ❌ Over-reliance on review papers (read primary sources)
- ❌ Insufficient citations (support all claims)
- ❌ Citation overkill (one citation per common statement)
- ❌ Inconsistent formatting (use reference manager)
- ❌ Broken or incorrect citations

---

## Version Control for References

### Track Changes
Keep dated backups of your bibliography:
```
references_backup_2025-01-15.bib
references_backup_2025-02-10.bib
```

### Export Regularly
- Export from reference manager weekly
- Backup to cloud storage
- Keep copy with thesis backup

---

## Final Reference List Checklist

Before submission:
- [ ] All in-text citations have corresponding entries
- [ ] All reference entries are cited in text
- [ ] Formatting is consistent throughout
- [ ] URLs are working (for online sources)
- [ ] DOIs are included (if required)
- [ ] Journal/conference names are properly abbreviated
- [ ] Author names are correctly formatted
- [ ] No duplicate entries
- [ ] Entries are in correct order (numbered for IEEE)
- [ ] Special characters render correctly
- [ ] All required fields are complete

---

## Useful Resources

### IEEE Reference Guide
https://ieeeauthorcenter.ieee.org/wp-content/uploads/IEEE-Reference-Guide.pdf

### Citation Management Tutorials
- Zotero: https://www.zotero.org/support/quick_start_guide
- Mendeley: https://www.mendeley.com/guides

### LaTeX Bibliography
- BibTeX tutorial: https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex
- biblatex (modern alternative): https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex

---

**Start building your reference library early!**
**Good reference management saves time and prevents headaches later.**
