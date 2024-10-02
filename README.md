# SentimentAnalysis
NLP Project - Sentiment Analysis by finetuning BERT pretrained model </br>
**Problem Statement** </br>
**Dataset:** https://huggingface.co/datasets/stanfordnlp/imdb
**BERT Architechture**</br>
![image](https://github.com/user-attachments/assets/ba232e6d-66ee-477f-bbc5-859f66d40669) </br>

BERT_model=BertForSequenceClassification(</br>
  (bert): BertModel(</br>
    (embeddings): BertEmbeddings(</br>
      (word_embeddings): Embedding(30522, 768, padding_idx=0)</br>
      (position_embeddings): Embedding(512, 768)</br>
      (token_type_embeddings): Embedding(2, 768)</br>
      (LayerNorm): LayerNorm((768,), eps=1e-12, elementwise_affine=True)</br>
      (dropout): Dropout(p=0.1, inplace=False)</br>
    )</br>
    (encoder): BertEncoder(</br>
      (layer): ModuleList(</br>
        (0-11): 12 x BertLayer(</br>
          (attention): BertAttention(</br>
            (self): BertSelfAttention(</br>
              (query): Linear(in_features=768, out_features=768, bias=True)</br>
              (key): Linear(in_features=768, out_features=768, bias=True)</br>
              (value): Linear(in_features=768, out_features=768, bias=True)</br>
              (dropout): Dropout(p=0.1, inplace=False)</br>
            )</br>
            (output): BertSelfOutput(</br>
              (dense): Linear(in_features=768, out_features=768, bias=True)</br>
              (LayerNorm): LayerNorm((768,), eps=1e-12, elementwise_affine=True)</br>
              (dropout): Dropout(p=0.1, inplace=False)</br>
            )</br>
          )</br>
          (intermediate): BertIntermediate(</br>
            (dense): Linear(in_features=768, out_features=3072, bias=True)</br>
            (intermediate_act_fn): GELUActivation()</br>
          )</br>
          (output): BertOutput(</br>
            (dense): Linear(in_features=3072, out_features=768, bias=True)</br>
            (LayerNorm): LayerNorm((768,), eps=1e-12, elementwise_affine=True)</br>
            (dropout): Dropout(p=0.1, inplace=False)</br>
          )</br>
        )</br>
      )</br>
    )</br>
    (pooler): BertPooler(</br>
      (dense): Linear(in_features=768, out_features=768, bias=True)</br>
      (activation): Tanh()</br>
    )</br>
  )</br>
  (dropout): Dropout(p=0.1, inplace=False)</br>
  (classifier): Linear(in_features=768, out_features=2, bias=True)</br>
  
) <br/>

**Distill - BERT Architechture**</br>
DistilBertModel(</br>
*Tabspace*(embeddings): Embeddings(</br>
*Tabspace**Tabspace*(word_embeddings): Embedding(30522, 768, padding_idx=0)</br>
    *Tabspace**Tabspace*(position_embeddings): Embedding(512, 768)</br>
    *Tabspace**Tabspace*(LayerNorm): LayerNorm((768,), eps=1e-12, elementwise_affine=True)</br>
    *Tabspace**Tabspace*(dropout): Dropout(p=0.1, inplace=False)</br>
 *Tabspace* )</br>
  (transformer): Transformer(</br>
   *Tabspace* (layer): ModuleList(</br>
     *Tabspace**Tabspace* (0-5): 6 x TransformerBlock(</br>
       *Tabspace**Tabspace**Tabspace* (attention): MultiHeadSelfAttention(</br>
        *Tabspace**Tabspace**Tabspace**Tabspace*  (dropout): Dropout(p=0.1, inplace=False)</br>
          (q_lin): Linear(in_features=768, out_features=768, bias=True)</br>
          (k_lin): Linear(in_features=768, out_features=768, bias=True)</br>
          (v_lin): Linear(in_features=768, out_features=768, bias=True)</br>
          (out_lin): Linear(in_features=768, out_features=768, bias=True)</br>
        )</br>
        (sa_layer_norm): LayerNorm((768,), eps=1e-12, elementwise_affine=True)</br>
        (ffn): FFN(</br>
          (dropout): Dropout(p=0.1, inplace=False)</br>
          (lin1): Linear(in_features=768, out_features=3072, bias=True)</br>
          (lin2): Linear(in_features=3072, out_features=768, bias=True)</br>
          (activation): GELUActivation()
        )
        (output_layer_norm): LayerNorm((768,), eps=1e-12, elementwise_affine=True)
      )
    )
  )
)
