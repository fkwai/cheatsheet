# Dropout in LSTM

Someone did Gal dropout: 
https://github.com/seba-1511/lstms.pth
https://github.com/salesforce/awd-lstm-lm/
https://github.com/ceshine/recurrent-dropout-experiments


LSTM dropout tutorial:
https://becominghuman.ai/learning-note-dropout-in-recurrent-networks-part-1-57a9c19a2307

Some benchmark / variant code
https://github.com/pytorch/benchmark


LSTM calling
 - forward:
    modules.rnn.RNNbase.forward
    -> _functions.rnn.RNN.forward
    1. if cudnn -> _functions.rnn.CudnnRNN
    2. if not cudnn 
        -> _functions.rnn.AutogradRNN.forward
        -> _functions.rnn.StackedRNN.forward
        -> _functions.rnn.Recurrent.forward


/home/kxf227/.local/lib/python3.5/site-packages/torch/nn/_functions/rnn.py

# build from source
https://github.com/pytorch/pytorch/blob/master/CONTRIBUTING.md

Add CUDA_HOME to specify CUDA directory:
export CUDA_HOME=/usr/local/cuda-9.0/

it will automatically create:
/home/kxf227/anaconda3/lib/python3.6/site-packages/easy-install.pth
/home/kxf227/anaconda3/lib/python3.6/site-packages/torch.egg-link.pth

with

/home/kxf227/work/GitHUB/pytorch

local virtual environment:
source activate local-pytorch
source deactivate
conda env list 

# git fork
https://help.github.com/articles/fork-a-repo/
https://help.github.com/articles/syncing-a-fork/
pull update from pytorch: git merge upstream/master

# add local package to python lib
create a .pth file to:
- Anaconda:
create /home/kxf227/anaconda3/lib/python3.6/site-packages/conda.pth
or 
conda develop $path
- pip:
/home/kxf227/.local/lib/python3.5/site-packages/package-kuai.pth