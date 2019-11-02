# PyTorch edit-distance functions

Useful functions for E2E Speech Recognition training with PyTorch and CUDA.

Here is a simple use case with Reinforcement Learning and RNN-T loss:

```python
hs = model.greedy_decode(xs, sampled=True)

pytorch_edit_distance.remove_blank(hs, xn, blank)

rewards = 1 - pytorch_edit_distance.wer(hs, ys, xn, yn, blank, space)

nll = rnnt_loss(zs, ys, xn, yn)

loss = nll * rewards
```

### levenshtein_distance

Levenshtein edit-distance with detailed statistics for ins/del/sub operations.

### remove_repetitions

Remove repeated tokens, useful for CTC-based model.

### remove_blank

Remove unnecessary blank tokens, useful for CTC, RNN-T, RNA models.

### strip_separator

Remove leading, trailing and repeated middle separators.

## Requirements

- C++11 compiler (tested with GCC 5.4).
- Python: 3.5, 3.6, 3.7 (tested with version 3.6).
- [PyTorch](http://pytorch.org/) >= 1.0.0 (tested with version 1.1.0).
- [CUDA Toolkit](https://developer.nvidia.com/cuda-zone) (tested with version 10.0).

## Install

There is no compiled version of the package. The following setup instructions compile the package from the source code locally.

### From Pypi

```bash
pip install pytorch_edit_distance
```

### From GitHub

```bash
git clone https://github.com/1ytic/pytorch-edit-distance
cd pytorch-edit-distance
python setup.py install
```