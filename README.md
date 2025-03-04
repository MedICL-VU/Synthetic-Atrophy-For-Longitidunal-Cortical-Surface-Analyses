# Synthetic Atrophy for Longitudinal Cortical Surfaces

An example workflow for this pipeline is located in Synthetic-Atrophy_example.sh. To compile this repository and run the example, you will need to download the following external packages:
- ITK:  https://itk.org/download/ (version 4.13.3 or later)
- VTK:  https://vtk.org/download/ (version 7.11 or later)
- c3d:  https://sourceforge.net/p/c3d/git/ci/master/tree/
- Slicer:  https://download.slicer.org/
- Greedy  https://sites.google.com/view/greedyreg/
- ImageMath: https://github.com/NIRALUser/niral_utilities/tree/master/ImageMath
- HoleDetection:  https://www.insight-journal.org/browse/publication/43 (click on "source code", then clone and compile")
cd
Once you download these tools, you'll need to update the appropriate paths in the CMakeLists.txt (ITK/VTK) and the example script (all others).


Once the paths have been updated and you've compiled the library, you can just run the Synthetic-Atrophy_example.sh to generate example data. The code is set to only atrophy the left superior temporal gyrus (LSTG) ROI (line 229), which is the example used in the paper, but you can apply this to any ROI within any cortical parcellation. All the steps are contained in the function main():
1. Set up paths/data and create masks for original timepoint
2. Get high resolution, cropped patch surrounding ROI
3. Induce atrophy and create masks for atrophy timepoint
4. Apply atrophy transform to image data
5. Create surface data for original/atrophy timepoints
6. Measure thickness change in surface data


If you use this tool, please cite the paper:

Synthetic Atrophy for Longitudinal Cortical Surface Analyses, K. E. Larson, I. Oguz. Frontiers in Neuroimaging, 2022.
https://doi.org/10.3389/fnimg.2022.861687