# MultiAttention-UNet

Sanitized source snapshot of an attention-based image-interpolation project. It compares pixel averaging, a random-forest baseline and PyTorch U-Net variants using SSIM and PSNR, with a Streamlit comparison interface.

## Source layout

- `Model_Func/`: multi-image U-Net, self/cross-attention components, decoder/encoder layers and diffusion-related experimental code.
- `Scripts/`: preprocessing, baseline training, neural training/inference and evaluation helpers.
- `Scripts/MultiAttention_Unet/`: an additional attention-architecture variant preserved separately from the older model package.
- `streamlit.py`: the original comparison interface.
- `setup.py`, `requirements.txt`: source installation metadata and original dependency constraints.

Legacy imports referencing a nonexistent `Class_Func` directory now refer to `Model_Func`; the nested attention package uses relative imports. These are packaging corrections in the public copy, not changes to the private repository.

## Reproduction

```bash
python -m pip install -r requirements.txt
python -m pip install -e .
streamlit run streamlit.py
```

These are launch instructions, not a verified end-to-end reproduction. Supply your own authorized image sequences/reference frames and train compatible models. The original UI references a Hugging Face model repository; availability and model/data permissions must be verified independently before enabling downloads. Direct deep-learning prediction expects local weights and sample frames that are intentionally absent here. Untrusted pickle/checkpoint files must not be loaded.

No training datasets, sample microscopy images, pretrained weights, plots or original notebook results are included. The original Git history is not exported. Python syntax was checked, but dependency installation, training, inference, external model downloads and SSIM/PSNR reproduction were not rerun. No numerical performance claims are made by this release.

## Relationship and attribution

This project and the earlier `540_Final` implementation belong to one attention-based image-interpolation experience group. The earlier public implementation is now named [Attention-Based-Image-Interpolation](https://github.com/Baze-Bai/Attention-Based-Image-Interpolation); they should not be counted as two separate experience entries.

The private original is retained unchanged. See `NOTICE.md` for source provenance and excluded artifacts. This source release uses the MIT license; dependencies and user-supplied data/weights retain their own terms.
