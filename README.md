This is a TensorFlow implementation of arbitrary order (>=2) Factorization Machine based on paper [Factorization Machines with libFM](http://dl.acm.org/citation.cfm?doid=2168752.2168771). 

It supports dense and sparse input. 


# Prerequisites
* [scikit-learn](http://scikit-learn.org/stable/)
* [numpy](http://www.numpy.org/)
* [TensorFlow 0.8](https://www.tensorflow.org/)
* [tqdm](https://github.com/tqdm/tqdm)

# Usage
The interface is the same as of Scikit-learn models. To train a 6-order FM model with rank=10 for 100 iterations with learning_rate=0.01 use the following sample
```
from tffm import TFFMClassifier
model = TFFMClassifier(
                order=6, 
                rank=10, 
                optimizer=tf.train.AdamOptimizer(learning_rate=0.01), 
                n_epochs=100, 
                batch_size=-1,
                init_std=0.001,
                input_type='dense'
        )
model.fit(X_tr, y_tr, show_progress=True)
```

See `example.ipynb` for details