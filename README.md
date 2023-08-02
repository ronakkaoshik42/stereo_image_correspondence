# Stereo Image Correspondence patching

Epipolar geometry implementation in python to get a fundamental matrix
and obtain a patched image of one of the stereo images’ pairs from the
other.
Steps:
1. Get the key points and the description vectors using SIFT and find
the pairs of matching points in the stereo pair.
2. Using the RANSAC algorithm, find the fundamental matrix using 8
random pairs of points and continue iteratively, finalizing on the best
fit (most inliers).
3. Find the epipolar lines for the source image from the reference
image.
4. Search the patches corresponding to each patch of a point of the
reference image in the source image by traversing the line in pixel
steps along the respective epipolar slope and return the closest one.
5. Patch a blank image with the patches taken from the source image
and of size of the reference image
