The computational challenges of handling and processing large-scale video datasets are currently the biggest barrier to developing accurate, reliable video classification systems. YouTube’s 8M dataset encompasses 0.5 million hours of video, 1.9 billion frame features, 4,800 classes, and amounts to 1.5 Terabytes of data – far larger than can be stored or processed on any individual machine. 

Our goal in this project was to develop a classification system capable of running in-parallel training in order to quickly and accurately classify the YouTube-8M dataset. We originally chose as our classification system a bi-directional Long Short-term Memory (LSTM) recurrent neural network (RNN), but due to the many customization steps necessary we settled on a simpler feedforward neural network. 

Our goal in developing a parallel deep learning architecture was to reduce the time necessary to train the model  to hours or even minutes. 
