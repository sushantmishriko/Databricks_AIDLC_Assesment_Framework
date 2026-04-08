# Frequently Asked Questions (FAQ)

## 🤔 General Questions

### Q1: What is this assessment framework?
**A:** A comprehensive tool to evaluate your current Genie Code usage across 11 AIDLC phases (59 questions). You provide scores and evidence; the framework generates maturity analysis, gap reports, visualizations, and an action plan.

### Q2: Why do I need this if I'm just inputting scores?
**A:** Great question! Here's the analogy:
- **Without framework**: Like having raw tax data in Excel - just numbers, no insights
- **With framework**: Like using TurboTax - it analyzes your data and generates comprehensive reports, identifies issues, provides recommendations

The framework AUTOMATES:
- Maturity scoring (overall + by phase)
- Gap analysis (what's critical vs. nice-to-have)
- Visualizations (radar charts, heatmaps)
- Prioritized roadmap (what to fix first)
- ROI calculations (time savings, cost reductions)
- Executive summaries (for leadership)

### Q3: How long does this take?
**A:** 
- **Your time**: 4-8 hours (review questions, test prompts, fill assessment)
- **Framework processing**: 2-5 minutes (automated)
- **Total benefit**: Saves weeks of manual analysis and roadmap planning

### Q4: Who should complete this assessment?
**A:** Involve multiple stakeholders:
- Data Engineers (Development, Deployment)
- BI Developers (BI Enablement, Semantic Layer)
- Claims Analysts (Business users of Genie)
- Data Architects (Governance, Design)
- MLOps Engineers (AI Governance)

---

## 📝 Completing the Assessment

### Q5: What do I fill in?
**A:** Only 4 columns (marked with ⚠️ YOU_FILL):
1. **Current_Score (1-5)**: Your honest rating of current Genie Code usage
2. **Evidence**: Specific proof (notebook IDs, query names, dashboard links)
3. **Notes**: Context, challenges, observations
4. **Priority**: For gaps (scores ≤3) - Critical/High/Medium/Low

### Q6: How do I score each question?
**A:** Read the Level_1_Criteria through Level_5_Criteria columns:
- **Score 1**: Not used, everything manual
- **Score 2**: Few people experimenting, not in production
- **Score 3**: Regular production usage, established patterns
- **Score 4**: Advanced usage, MCP customization, high expertise
- **Score 5**: Industry-leading, fully autonomous

**Key**: Score CURRENT USAGE, not potential or future plans.

### Q7: What if I don't have evidence for everything?
**A:** That's okay! Evidence is most important for scores ≥3. If you score 1-2, it indicates minimal usage, so lack of evidence is expected. Focus evidence on areas where you score 3+.

### Q8: Should I test the Example_Prompts?
**A:** YES! Testing prompts with your insurance/claims data helps calibrate your scores. Copy prompts into Genie Code and observe:
- Does it generate useful output?
- Do you currently use this capability in production?

### Q9: What if my domain isn't insurance?
**A:** The prompts are insurance-focused (claims, policies, fraud) but the assessment applies to any domain. Adapt prompts to your context:
- Insurance → Retail: "claims_data" → "order_data"
- Insurance → Healthcare: "policy_holders" → "patients"

---

## 🎯 Understanding Scores

### Q10: What's a good score?
**A:** Target maturity levels:
- **1.0-1.9**: Initial/Manual (needs significant work)
- **2.0-2.9**: Experimental (good start, needs standardization)
- **3.0-3.9**: Defined (solid foundation, focus on optimization)
- **4.0-4.9**: Optimized (mature adoption, explore innovation)
- **5.0**: Leading (industry-leading, share best practices)

### Q11: Should I aim for 5.0 everywhere?
**A:** No! Level 5 is industry-leading and not necessary for all areas. Target:
- Critical phases (Development, Governance): 3.5+
- Supporting phases (Deployment, Monitoring): 3.0+
- Advanced phases (MCP, Complex Use Cases): 2.5+ (these are newer)

### Q12: What if I score low?
**A:** Low scores are GOOD for this assessment because they identify improvement opportunities! The framework will:
- Prioritize gaps by business impact
- Suggest quick wins (1-2 months)
- Provide step-by-step roadmap
- Estimate ROI for improvements

---

## 🤖 Framework Processing

### Q13: What happens after I complete the assessment?
**A:** You upload the completed CSV and run the Config Reader notebook, which:
1. Validates your input
2. Calculates maturity scores
3. Identifies critical gaps
4. Generates visualizations
5. Creates prioritized action plan
6. Produces executive summary
7. Exports reports

### Q14: What outputs does the framework generate?
**A:** 
- **Maturity Dashboard**: Overall score + 11 phase scores
- **Gap Analysis Report**: Critical gaps sorted by priority
- **Radar Chart**: Visual spider chart of maturity across phases
- **Heatmap**: Color-coded grid (red=gaps, green=strengths)
- **Action Plan**: Prioritized roadmap with timelines
- **Executive Summary**: Business-friendly summary for leadership
- **ROI Projections**: Time savings and cost reductions

### Q15: Can I customize the framework?
**A:** Yes! The framework is extensible:
- Add custom questions to the CSV
- Modify maturity criteria
- Adjust scoring algorithms in the notebook
- Add domain-specific visualizations

---

## 📊 Results and Next Steps

### Q16: How do I interpret results?
**A:** The framework provides clear interpretations:
- Overall score shows your maturity level
- Phase scores show strengths and weaknesses
- Gap analysis highlights what to fix first
- Action plan provides specific next steps

### Q17: What should I do with the results?
**A:** 
1. **Review with team**: Validate findings
2. **Present to leadership**: Use executive summary + charts
3. **Prioritize improvements**: Focus on critical gaps first
4. **Start quick wins**: 1-2 month improvements
5. **Plan strategic initiatives**: 6-12 month projects
6. **Track progress**: Re-assess in 6 months

### Q18: How often should I run this assessment?
**A:** 
- **Initial**: Establish baseline
- **3 months**: Check quick win progress
- **6 months**: Comprehensive re-assessment
- **Annually**: Track long-term maturity growth

---

## 🏥 Insurance-Specific

### Q19: Why are all examples insurance-focused?
**A:** The assessment was designed for insurance clients (claims processing, fraud detection, policy management). But the questions apply to ANY industry - just adapt the prompts.

### Q20: What insurance concepts are covered?
**A:** 
- Claims processing (intake, adjudication, payment)
- Fraud detection (scoring, anomalies)
- Policy management (multi-line products)
- Compliance (HIPAA, PII protection)
- Metrics (Loss Ratio, IBNR, Claim Severity)
- Adjuster workflows
- Multi-carrier architectures

---

## 🔧 Technical Questions

### Q21: Do I need special Databricks permissions?
**A:** You need:
- Access to Genie Code
- Unity Catalog read access (for testing prompts)
- Ability to upload files to workspace
- Ability to run notebooks

### Q22: Which file format should I use - CSV or Excel?
**A:** 
- **CSV**: Recommended - works on all systems, fastest to process
- **Excel**: Easier to edit, but ensure it exports cleanly to CSV

### Q23: What if the CSV columns appear blank in Excel?
**A:** The CSV is UTF-8 encoded. In Excel:
1. Use "Data" → "From Text/CSV"
2. Select UTF-8 encoding
3. Or use Google Sheets (handles UTF-8 natively)

---

## 💡 Tips for Success

### Q24: Any tips for accurate scoring?
**A:** 
✓ Be honest (assessment helps YOU)
✓ Involve multiple team members
✓ Test prompts before scoring
✓ Document specific evidence
✓ Focus on production usage, not experiments
✓ Review as a team before finalizing

### Q25: What if team members disagree on scores?
**A:** Great! Disagreements reveal valuable insights:
1. Discuss different perspectives
2. Review evidence together
3. Reach consensus or average scores
4. Document reasons for final score in Notes

---

## 📞 Getting Help

### Q26: Who do I contact for support?
**A:** Contact your Tiger Analytics engagement lead for:
- Technical questions about scoring
- Help interpreting results
- Custom requirements
- Training on Genie Code capabilities

### Q27: Can I see a sample completed assessment?
**A:** Yes! Check the folder for `SDLC_Assessment_SAMPLE.csv` which shows an example Level 2 organization with completed scores and evidence.

---

## 🚀 Success Stories

### Q28: What results have other clients seen?
**A:** Typical outcomes after 6 months:
- **Maturity improvement**: 1.8 → 3.2 average
- **Time savings**: 15-20 hours/week per team
- **Productivity**: 30% faster pipeline development
- **Quality**: 40% reduction in data quality issues
- **Fraud detection**: 25% improvement in detection rates

---

© Tiger Analytics 2024 | FAQ v3.0
