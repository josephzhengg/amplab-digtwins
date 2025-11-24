# Steps to Reproduce Results

This document outlines the steps to reproduce the results presented in this repository.

!!! danger "Important Info"

    Make sure you're running these steps in a system that can handle the computational load, as EEG data processing and GAN training can be resource-intensive. GPUs are recommended for training GAN models as well as having sufficient RAM for data processing.

1.  **Clone the Repository**: Start by cloning the repository to your local machine.

    ```bash
    git clone https://github.com/josephzhengg/amplab-digtwins.git
    cd amplab-digtwins
    ```

2.  **Install Dependencies**: Install the required Python packages using pip.

    ```bash
    pip install -r requirements.txt
    ```

3.  **Data Acquisition**: Download the raw EEG data from the Healthy Brain Network (HBN) dataset (release 10) found [here](https://nemar.org/dataexplorer/detail?dataset_id=ds005515){:target="\_blank"} and place all raw data files in the `raw/` directory.

4.  **Data Preprocessing**: Use the `filter.ipynb` and `processed_filter.ipynb` notebooks to preprocess the raw EEG data.

    !!! info "Notebooks Used"

        - `filter.ipynb`: Performs low-pass filtering and artifact removal using ASR. (Saves to `processed/` directory)

        - `processed_filter.ipynb`: Performs channel selection and further filtering of processed data. (Saves to `filtered_processed/` directory)

5.  **Task Separation**: Utilize the `separate_tasks_resting_state.ipynb` notebook to separate different tasks (e.g., eyes open vs. eyes closed) from the resting-state EEG data.

6.  **GAN Training**: Train GAN models on the resting-state EEG data using the `resting_state_gans.ipynb` notebook. The generated models will be saved in the `gan_data/` directory.

7.  **Generate Synthetic Data**: Use the trained GAN models to generate synthetic EEG data samples, which will be saved in the `synthetic_data/` directory (this will automatically be done in the GAN training notebook).

Every single step and notebook is designed to flow seamlessly into the next, so following these steps in order should allow you to reproduce the results effectively. Again, this repo wants to encourage experimentation, so feel free to modify the notebooks and explore different configurations!
