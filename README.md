# CS 6320 Project 2: Detecting Lines and Circles with the Hough Transform

## Setup

0. Unzip the project and enter its folder: `unzip proj2_6320.zip && cd proj2_6320`
1. Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) if you do not have conda.
2. Create the environment: `conda env create -f proj2_env.yml`
   On Windows run this from the "Anaconda Prompt"; on macOS and Linux any terminal works.
3. Activate it: `conda activate proj2`
4. Start Jupyter from this folder with `jupyter notebook`, then open
   `proj2_code/Project_2_CS6320.ipynb`. The notebook uses paths relative to `proj2_code/`
   (`../data/`, `../results/`), so leave it where it is.
5. Answer every question in the notebook, including the AI-use disclosure at the end. The notebook
   is the report: run all cells before you submit so the figures and printed output are saved.
6. Build your submission: `python zip_submission.py --uid <your_uid>`

## Notes

- The `results/Ques_1` through `results/Ques_6` folders are created by the setup cell, and every
  save goes through `save_and_show()`, which raises if the write fails instead of failing silently.
- Do not use a library implementation of the Hough transform. `cv.HoughLines`, `cv.HoughLinesP`,
  `cv.HoughCircles` and `skimage.transform.hough_*` are all off limits. Convolution, drawing and
  file I/O from OpenCV are fine.
- Vectorize the voting loops. A direct double loop over edge pixels and angles takes minutes per
  call; handling all edge pixels at once with NumPy brings it under a second, and Q5 calls the
  detectors dozens of times.
- `data/` contains three synthetic images for debugging. They are not graded, but a detector that
  misbehaves on a photograph is much easier to diagnose on a picture with three clean lines in it.
- Please do not install extra packages: the graders run this exact environment.
