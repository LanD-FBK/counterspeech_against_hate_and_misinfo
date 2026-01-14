# counterspeech_against_hate_and_misinfo

# Dataset description

This is a demonstration subset of the dataset related to the 10207 TACL submission "Assisted Counterspeech Writing at the Crossroads of Hate Speech and Misinformation".

Each entry in the dataset contains **12 fields**:

- **`pair_id`**: Unique identifier for the claim–counterspeech pair.  
- **`claim`**: A hateful claim containing misinformation.  
- **`CS_gen`**: Automatically generated counterspeech responding to the claim.  
- **`CS_ed`**: Expert-revised version of the counterspeech.  
- **`generation_strategy`**: Strategy used to generate the counterspeech. Possible values are `Fact-Checkers`, `NGO`, or `Mixed`.  
- **`target`**: Marginalised group targeted by the claim.  
- **`antistereotype_id`**: List of unique IDs for the anti-stereotypes used as external knowledge for this pair.  
- **`fc_article_id`**: Unique ID of the fact-checking article used as external knowledge.  
- **`annotator_type`**: Type of expert who revised the counterspeech: fact-checker (`FC`) or NGO operator (`NGO`).  
- **`fc_article_url`**: Source URL of the fact-checking article.  
- **`antistereotype_url`**: List of source URLs for the anti-stereotypes used.  
- **`antistereotype_location`**: Location of the specific anti-stereotype within the corresponding antistereotype source URL.  
  For example, an antistereotype location value of `"2"` for the antistereotype URL  
  `https://www.adl.org/sites/default/files/myths-and-facts-about-muslim-people-and-islam.pdf`  
  refers to *Myth #2* in that page.
