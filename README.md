# GRACE CLI

GRACE CLI is a tool for processing NIfTI (.nii or .nii.gz) files using [GRACE model](https://github.com/lab-smile/GRACE), batch processing is also supported.

## Prerequisites

- Python 3.1x
- Ability to create virtual environments (`python3-venv`)

## Installation

1. Clone this repository:
```bash
git clone [repository-url]
cd grace-cli
```

2. Make sure the run script is executable:
```bash
chmod +x run.sh
```

3. Download `GRACE.pth` file from the following build to `grace-cli` directory.
```bash
https://github.com/lab-smile/GRACE/releases/tag/v1.0.1
```

## Usage

The tool can be run using the provided shell script:

```bash
./run.sh <input_nifti_file.nii.gz> or <folder_path_to_nifti_images>
```

For example:
```bash
./run.sh sample_image.nii.gz
./run.sh ./input_folder
```

### What the script does:

1. Creates a Python virtual environment
2. Installs all required dependencies
3. Processes the input NIfTI file(s)
4. Outputs the results in the `outputs` folder in the current directory.

### Output

The processed files will be saved in the `outputs` directory with the following naming convention:
- `<input_filename>_pred_GRACE.nii(.gz)`: NIfTI format output

## Error Cases

The script will show an error message if:
- No input file is provided
- The input file doesn't exist
- The input file is not a .nii.gz or .nii file
- Input is neither a file nor a folder with NIfTI images

## Dependencies

All required Python packages are listed in `requirements.txt` and will be automatically installed in the virtual environment when running the script.

## Notes

- The script automatically handles the creation and cleanup of the Python virtual environment
- Each run creates a fresh virtual environment to ensure consistency
- GPU support is available if CUDA is properly configured on your system
- Change `python` command in `run.sh` if command installed on your machine is `python3.x`
- If you are running on hipergator make sure you have >=python3.10 loaded, you can load it using `module load python/3.10`
