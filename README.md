# PeeriScope: A Multi-Faceted Framework for Evaluating Peer Review Quality

PeeriScope is a modular framework for evaluating the quality of scholarly peer reviews, accepted as a demo paper at The Web Conference (WWW) 2026. It combines interpretable structured metrics, rubric-guided large language model assessments, and supervised prediction to provide a multidimensional view of review quality beyond simple accept/reject signals. Designed for transparency, scalability, and easy integration, PeeriScope supports reviewer self-assessment, editorial triage, and large-scale auditing through both an interactive web interface and a programmatic API. This repository provides the official API documentation and usage guidelines, enabling seamless integration into editorial and research workflows.

💻 The live platform is available at [https://app.reviewer.ly/app/peeriscope](https://app.reviewer.ly/app/peeriscope).

---

## API Documentation
PeeriScope offers three easy-to-use API endpoints tailored to your workflow. The **Manual API** enables you to submit a paper’s title and abstract, the text of a review, and optional reviewer details, allowing it to compute a suite of quantifiable quality metrics. The **LLM API** accepts the same inputs but leverages large language models to deliver deeper, context-aware analysis of each review. And the **OpenReview API** requires only the URL of an OpenReview submission—it automatically retrieves every reviewer report for that manuscript and runs the full suite of quality assessments on them.

⚙️ You can access the endpoint for this API at: [https://app.reviewer.ly/apis/peeriscope](https://app.reviewer.ly/apis/peeriscope)

### API Example Request - Manual Mode
```json
{
  "review": "string",
  "title": "string",
  "abstract": "string",
  "reviewer_openalex_id": "string",
  "reviewer_name": "string"
}
```

### API Example Response - Manual Mode
```json
{
  "review_length": 0,
  "mattr_score": 0,
  "question_count": 0,
  "citation_count": 0,
  "sentiment_score": 0,
  "politeness_score": 0,
  "similarity_score": 0,
  "readability_score": 0,
  "hedging_score": 0,
  "explicit_reference_count": 0,
  "reviewer_openalex_id": "string",
  "reviewer_name": "string",
  "reviewer_citation_count": 0,
  "reviewer_h_index": 0,
  "reviewer_academic_career_length": 0,
  "general_alignment": 0,
  "in_depth_alignment": 0,
  "recency_alignment": 0,
  "predicted_overall_quality_score": 0
}
```

### API Example Request - Manual Mode LLM
```json
{
  "review": "string",
  "title": "string",
  "abstract": "string",
  "reviewer_openalex_id": "string",
  "reviewer_name": "string"
}
```

### API Example Response - Manual Mode LLM
```json
{
  "comprehensiveness": 0,
  "usage_of_technical_terms": 0,
  "factuality": "string",
  "sentiment_polarity": "string",
  "politeness": "string",
  "vagueness": "string",
  "objectivity": 0,
  "fairness": 0,
  "actionability": 0,
  "constructiveness": 0,
  "relevance_alignment": 0,
  "clarity_and_readability": 0,
  "overall_quality": 0
}
```


### API Example Request - OpenReview
```json
{
  "url": "string"
}
```

### API Example Response - OpenReview
```json
{
  "analysis_results": [
    {
      "quantifiable_analysis": {
        "review_length": 0,
        "mattr_score": 0,
        "question_count": 0,
        "citation_count": 0,
        "sentiment_score": 0,
        "politeness_score": 0,
        "similarity_score": 0,
        "readability_score": 0,
        "hedging_score": 0,
        "explicit_reference_count": 0,
        "reviewer_openalex_id": "string",
        "reviewer_name": "string",
        "reviewer_citation_count": 0,
        "reviewer_h_index": 0,
        "reviewer_academic_career_length": 0,
        "general_alignment": 0,
        "in_depth_alignment": 0,
        "recency_alignment": 0,
        "predicted_overall_quality_score": 0
      },
      "llm_analysis": {
        "comprehensiveness": 0,
        "usage_of_technical_terms": 0,
        "factuality": "string",
        "sentiment_polarity": "string",
        "politeness": "string",
        "vagueness": "string",
        "objectivity": 0,
        "fairness": 0,
        "actionability": 0,
        "constructiveness": 0,
        "relevance_alignment": 0,
        "clarity_and_readability": 0,
        "overall_quality": 0
      },
      "review_text": "string",
      "reviewer_name": "string"
    }
  ],
  "paper_title": "string",
  "paper_abstract": "string"
}
```

## Citation
If you use this dataset in academic work, please cite our paper.

```bibtex
@inproceedings{ebrahimi2026peeriscope,
  title={PeeriScope: A Multi-Faceted Framework for Evaluating Peer Review Quality},
  author={Ebrahimi, Sajad and Sadeghian, Soroush and Ghorbanpour, Ali and Arabzadeh, Negar and Salamat, Sara and Hosseini, Seyed Mohammad and Le, Hai Son and Bashari, Mahdi and Bagheri, Ebrahim},
  booktitle={Companion Proceedings of the ACM Web Conference 2026 (WWW Companion '26)},
  series = {WWW '26},
  year={2026},
  url = {https://doi.org/10.1145/3774905.3793128},
  doi = {10.1145/3774905.3793128}
}
```
