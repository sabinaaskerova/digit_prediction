# Convolutional Neural Network (CNN) for Digit Recognition

This project uses CNN (TensorFlow, Keras) to recognize digits from the MNIST dataset. 

The neural network is built using the Sequential API of Keras.

Convolutional and Pooling Layers:

- The first convolutional layer with 32 filters of size (3, 3), ReLU activation, and input shape (28, 28, 1).

- Max pooling layer with a pool size of (2, 2).

- The second convolutional layer with 64 filters of size (3, 3) and ReLU activation.

- Another max pooling layer with a pool size of (2, 2).

Flatten and Dense Layers:

- A flatten layer to convert the 2D feature maps into a 1D vector.

- A dense layer with 64 neurons and ReLU activation.

- The final dense layer with 10 neurons (number of classes) and softmax activation for multi-class classification.

Model Compilation

The model is compiled using the Adam optimizer, categorical crossentropy as the loss function, and accuracy as the metric to monitor during training.

```
model.compile(optimizer='adam',
              loss='categorical_crossentropy',
              metrics=['accuracy'])
```

Model Training

The training process involves fitting the model to the training data for 5 epochs with a batch size of 64. 
The validation split is set to 20% to monitor performance on a validation subset.

```
model.fit(train_images.reshape(-1, 28, 28, 1), train_labels, epochs=5, batch_size=64, validation_split=0.2)
```

# Results
```
Test accuracy: 0.9891999959945679
Test loss:0.034049030393362045
```

<img width="700" src=https://github.com/sabinaaskerova/digit_prediction/assets/91430159/47f9c3f5-cf4e-4339-acd2-85b4b5406421>

I also tested the model to see if it can predict the digits written by myself.
<br>
<img width="100" src=https://github.com/sabinaaskerova/digit_prediction/assets/91430159/4ae9dc4a-e9e0-498a-bbac-b754fb7a99e4>
<img width="100" src=https://github.com/sabinaaskerova/digit_prediction/assets/91430159/562bfcee-3472-4b6d-89c2-5b2384fafacf>
<img width="100" src=https://github.com/sabinaaskerova/digit_prediction/assets/91430159/89b7b0ec-a54c-42af-81c9-2ac2fb18a1a8>
<img width="100" src=https://github.com/sabinaaskerova/digit_prediction/assets/91430159/47959c86-ae6b-4006-ba8c-639fe0e28a35>
<img width="100" src=https://github.com/sabinaaskerova/digit_prediction/assets/91430159/0c97d2fb-6bf5-413b-9a4f-e11125656d74>



While exploring the data, I observed that most sevens in the dataset were written without a horizontal bar. There was a vsible lack of horizontal-bar-sevens in the dataset (the way I personally write it).
![Screenshot from 2024-03-08 22-22-36](https://github.com/sabinaaskerova/digit_prediction/assets/91430159/ba1d8341-dfa4-4e71-8eed-37fb2326c5f4)

And it turned out to be more difficult for a model to recognize such sevens (on the left). 
<img width="500" src=https://github.com/sabinaaskerova/digit_prediction/assets/91430159/4e660e32-e9d4-4953-87ed-46dfaad526ce>

I also presented an extreme case of writing a '3' digit to the model and it had hard time recognizing it to (also possibly due to poor picture quality)
<img width="500" src=https://github.com/sabinaaskerova/digit_prediction/assets/91430159/b7bbf33f-fa54-43ae-8eed-068b2993feb0>
