🧠 English to Spanish Translator using LSTM (TensorFlow)
This project is a simple sequence-to-sequence (seq2seq) neural machine translation model built using TensorFlow. It translates English sentences into Spanish using LSTM-based encoder-decoder architecture. The dataset used is the spa-eng parallel corpus, which consists of thousands of sentence pairs.

🚀 Features
LSTM-based encoder-decoder architecture

Text vectorization using TextVectorization layers

Embedding layers with masking support

Manual extraction of dataset for better visibility (e.g., in Google Colab)

Simple greedy decoding for translation

Easily extendable to attention mechanisms or Transformer models

📁 Dataset
The dataset is downloaded from TensorFlow’s public storage and contains English-Spanish sentence pairs:

arduino
Copy
Edit
https://storage.googleapis.com/download.tensorflow.org/data/spa-eng.zip
🛠️ Model Architecture
Encoder: Embedding → LSTM (returns hidden state)

Decoder: Embedding → LSTM (initialized with encoder state) → Dense (Softmax over vocab)

Loss: Sparse Categorical Crossentropy

Optimizer: Nadam

🧪 Training
The model is trained on 100,000 sentence pairs, vectorized with a vocabulary size of 1000 and padded to a max length of 50 tokens.

python
Copy
Edit
model.fit((X_train, X_train_dec), Y_train, epochs=10,
          validation_data=((X_valid, X_valid_dec), Y_valid))
🔤 Example Usage
python
Copy
Edit
translate("I like cars")     # returns: "me gustan los coches"
translate("I like soccer")   # returns: "me gusta el fútbol"
Note: Translations may not be perfect. This is a minimal working demo, and accuracy can be improved using attention or larger datasets.

📚 Future Improvements
Add attention mechanism (Bahdanau or Luong)

Replace LSTM with Transformer layers

Export to ONNX / TFLite for lightweight inference

Build web demo with Gradio or Streamlit

📄 License
This project is for educational purposes and is open source under the MIT License.
