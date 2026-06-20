# Counterspeech datasets against hate and misinformation
This page contains several expert-curated datasets for fighting online hate and misinformation through counterspeech (CS). For each dataset we provide a description of its characteristics, the data, and the corresponding publication.

# Pairs with fact-checking, NGO and mixed strategy CS
This is the dataset related to the paper "Assisted Counterspeech Writing at the Crossroads of Hate Speech and Misinformation".

## Dataset description
Each entry in the dataset contains **13 fields**:

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
- **`HTER`**: contains the HTER score computed using the pyter3 library between `CS_gen` and `CS_ed`. Pairs with a HTER value >= 0.39 were selected for the human evaluation addressing RQ1.

## Citation
```
@article{martone2026assisted,
  title={Assisted Counterspeech Writing at the Crossroads of Hate Speech and Misinformation},
  author={Martone, Genoveffa and Bonaldi, Helena and Guerini, Marco},
  journal={arXiv preprint arXiv:2605.22435},
  year={2026}
}
```

# CATCH-ME
This is the dataset related to the paper "CATCH-ME if you RAG: a dataset of Contextually Annotated multi-Turn Counterspeech against Hate and Misinformation Exchanges".

## Dataset description
Each entry in the dataset corresponds to a dialogue, and contains the following fields. 
- `parent`: if different from 0, the `id` of the parent dialogue (i.e. the post-edited dialogue of which the current dialogue is a modification itself)
- `id`: dialogue id 
- `task_id` and `task_name`: id and name of the task in the annotation platform (multiple dialogue ids can be part of the same task, and share same external knowledge)
- `language`: dialogue language, English (`en`), Spanish (`es`), Italian (`it`), Maltese (`mt`) or Polish (`pl`)
- `project_id`: id of the project. Different dialogues are grouped into projects, usually according to language and/or generation strategy (Polish Interactive, English Pre-compiled, etc.)
- `normalised_document_name`: list of names of documents used as external knowledge in that dialogue
`normalised_document_name` never is).
- `TARGET`: list of the marginalised group(s) to which is document is referred
- `URL` and `flat_url`: list of source urls of each document. For the NGO reports, it is a list of lists with the source url of each document referenced in the same NGO report. So if a dialogue references one NGO report, the `url` will be: `[[anti-stereotype-url-1, anti-stereotype-url-2, ...]]`. If it references both a fact-checking article and an NGO report, `url` will be: `[fact-checkingarticle-url, [anti-stereotype-url-1, anti-stereotype-url-2, ...]]`. the `flat` version contains the flattened version of `url`.
- `permanent_url`: the archived version of the url (created with Wayback machine or Archive.is)
- `CLAIM`: list with the claim of each document related to the dialogue
- `nr_turns` and `nr_cs`the number of total turns in the dialogue and of counterspeech turns.
- `file_id`: list of unique ids identifying the files linked to that dialogue, created by the annotation platform. The same file has different `file_id` if uploaded to different projects.
- `doc_id`: list of unique ids identifying the same document across the entire dataset. It is based on the source url, so the same document uploaded to different projects will have the same `doc_id`
- `annotation_strategy`: what strategy has been employed for annotation. Either Pre-compiled, Interactive, Manual or Translation.
- `annotations`: contains a dictionary with two main keys: `data` and `time`. `time` contains the annotation time in seconds, while `data` contains a list with a dictionary for each turn, each containing the following keys:
    - `speaker`: either `speaker_1` (hate/misinformation) or `speaker_2` (counterspeech)
    - `text`: turn text post-edited by annotators
    - `file_id` list of file ids of the documents that the turn uses as external knowledge
- `original_dialogue`: contains the generated dialogue (when present) before post-editing. Same structure as `annotations['data']` content.


## Citation
```
@article{bonaldi2026catch,
  title={CATCH-ME if you RAG: a dataset of Contextually Annotated multi-Turn Counterspeech against Hate and Misinformation Exchanges}, 
  author={Helena Bonaldi and Genoveffa Martone and Marco Guerini},
  journal={arXiv preprint arXiv:2606.20369},
  year={2026}
}
```