# Effi-ProPainter
Effi-ProPainter is an optimized version of the original ProPainter, enhancing GPU VRAM efficiency and enabling inference at higher parameter settings without encountering out-of-memory (OOM) issues. Effi-ProPainter uses only approximately 60% of the peak GPU VRAM consumption compared to the original ProPainter.

## Installation
The basic setup and installation procedures are identical to those of the original [ProPainter](https://github.com/sczhou/ProPainter).

1. Clone Repo

   ```bash
   git clone https://github.com/kimx3966/Effi-ProPainter.git
   ```

2. Create Conda Environment and Install Dependencies

   ```bash
   # create new anaconda env
   conda create -n propainter python=3.8 -y
   conda activate propainter

   # install python dependencies
   pip3 install -r requirements.txt
   ```

   - CUDA >= 9.2
   - PyTorch >= 1.7.1
   - Torchvision >= 0.8.2
   - Other required packages in `requirements.txt`


## Inference
Run the following commands to try it out:
```shell
# The first example (object removal)
python inference_effi_propainter.py --video inputs/object_removal/bmx-trees --mask inputs/object_removal/bmx-trees_mask 
# The second example (video completion)
python inference_effi_propainter.py --video inputs/video_completion/running_car.mp4 --mask inputs/video_completion/mask_square.png --height 240 --width 432
```

## Further Optimized Memory-efficient Inference
The following options provide additional ways to reduce GPU VRAM usage. Unless stated otherwise, the content below is identical to the original [ProPainter](https://github.com/sczhou/ProPainter):

   - Reduce the number of local neighbors through decreasing the `--neighbor_length` (default 10).
   - Reduce the number of global references by increasing the `--ref_stride` (default 10).
   - Set the `--resize_ratio` (default 1.0) to resize the processing video.
   - Set a smaller video size via specifying the `--width` and `--height`.
   - Set `--fp16` to use fp16 (half precision) during inference.
   - Reduce the frames of sub-videos `--subvideo_length` (default 80), which effectively decouples GPU memory costs and video length.


## License
Please be aware that ProPainter is governed by the non-commercial [S-Lab license](https://github.com/sczhou/ProPainter/blob/main/LICENSE).

## Acknowledgement
This implementation is built upon [ProPainter](https://github.com/sczhou/ProPainter). Huge thanks to the original authors for their impressive contribution!