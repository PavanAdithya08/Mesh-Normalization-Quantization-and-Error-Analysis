# Mesh-Normalization-Quantization-and-Error-Analysis
Mesh Normalization and Quantization Analysis
This notebook demonstrates mesh normalization and quantization techniques, including a comparison between uniform and adaptive quantization methods under mesh transformations.

How to Run the Code
Upload Mesh File:

Ensure the cylinder.obj file is present in the /content/ directory of your Colab environment. If not, upload it using the file browser on the left sidebar.
Note: If cylinder.obj is not found, the notebook will automatically generate a default trimesh cylinder as a fallback, but for optimal results and to reproduce original findings, please upload the cylinder.obj file.
Execute Cells Sequentially:

Go to Runtime -> Run all to execute all the cells in the notebook from top to bottom.
Alternatively, you can run each cell individually.
View Visualizations:

Interactive Plotly visualizations will be displayed directly within the notebook output cells for the original, normalized, and reconstructed meshes.
Error comparison charts (MSE and MAE) will also be displayed using Plotly.
Review Analysis:

The notebook includes markdown cells with detailed analysis, comparison tables, and a comprehensive summary of the findings.
Key Observations
Initial Normalization & Quantization:
Both Min-Max and Unit Sphere normalization methods effectively scaled the mesh. Unit Sphere normalization resulted in slightly lower Mean Squared Error (MSE), while Min-Max had slightly lower Mean Absolute Error (MAE) for the initial mesh.
Reconstruction after uniform quantization with a bin size of 1024 yielded high fidelity for both methods.
Advanced Challenge: Rotation and Translation Invariance + Adaptive Quantization:
Unit Sphere Normalization Invariance: Unit Sphere normalization proved highly robust to rigid transformations. Reconstruction errors for uniformly quantized transformed meshes remained remarkably consistent and low, demonstrating that the normalization effectively makes the mesh's representation independent of its pose.
Adaptive vs. Uniform Quantization: For the cylinder.obj mesh, uniform quantization consistently performed better than the implemented CDF-based adaptive quantization. Uniform quantization resulted in significantly lower MSE and MAE values across all original and transformed meshes.
This suggests that for meshes with relatively uniform vertex distributions like a cylinder, a simpler uniform binning strategy is more effective in preserving detail and minimizing reconstruction error.
Adaptive quantization, while conceptually designed to reduce information loss in non-uniform distributions, did not show an advantage in this specific scenario, potentially due to the mesh's geometry or the specific adaptive implementation.
