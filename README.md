# Multiclass-Image-Classification-on-Leaves
a solution is developed which uses the concept of the Hu moments invariant and the Haralick feature descriptors to perform image classification on the images in the Leafsnap dataset

the model manages to achieve good segmentation

top-1 accuracy score lies around 0.52

top-5 accuracy score is around 0.81

check the **Segmentation_Results** folder to see samples of the segmentations
# How To Use:
## quickly testing out the system:
* Download the notebook and the **split_by_purpose** folder containing train.csv and test.csv. Store the notebook and the split_by_purpose folder in the root directory of the project (a folder of your choice)
* Navigate to the section "Model Definition" and set the root dir value to be the root directory of this project within your system, i.e the folder housing the notebook and the split_by_purpose folder.
* run the blocks of code in **Model Definition**. the upgrade scikit block is needed to access the top-k accuracy scores in Google Colab.
* Run the blocks of code in the **Training** section. If root dir is set correctly, the program will identify the train file and use it. Make sure the notebook has access to the folder location (e.g in if storing in Google Drive, grant access to the drive to the notebook)
* You may now run the **Evaluation** code segments. These blocks will show test the classifier on the testing subset. 
* You may also now make use of the user-facing function "classify()" in the very last section. Simply swap out the string value of leaf_image_path for the path of an image that is accessible to the notebook. running this section will then produce a result for any image handed to it (although results may not reflect the accuracy obtained by the evaluation phase, as this testing was performed on data that was comparable if not similar in nature to the training set, since they came from the same dataset)
## testing out from scratch:
* download the notebook.
* make a root directory to store all the data generated by the model. Ideally, store the notebook in this folder.
* set the value of root_dir in the notebook to be the path of this directory (make sure to set it both in the first code block and again in the Model Definition section)
* download the leafsnap dataset and place the "dataset" folder in the root directory.
* run the sections in the notebook. Occasionally, where a pip command is used, you will be instructed to restart the runtime. If you are sure that your runtime does not need to update or install the library, you may ignore/comment out this pip command. If you have already run the pip command and restarted the runtime, you can comment out the pip command. 
* The initial sections: **Segmentation and Preprocessing**, **Feature Extraction**, and **Train Test Split**, are all designed to work independently of each other. If you have completed running one section and then closed/crashed/ you need not run it again in order to move on to the next
* several blocks of code need to iterate through large lists of images. Where these blocks are known to take a long time to execute, a variable start_at is provided. If your runtime crashes midway through execution, you may set the value of start_at to be such that no repetition is done when re-running. please note that in the case of feature extraction, saves are only made after every 500 items (multiple of 500), so if a feature extraction function crashes, you need to set start_at to be the last multiple of 500 that was completed, instead of the actual last index that is printed as complete.
* From here, as long as the folder structure is preserved and all files are in place, the steps are the same as the quick usage steps (from the third step onwards). If you want to make use of a different model than Random Forest, simply swap the line model=model_RFC for model=M where M is the name of the model you want to use (bear in mind this will only work with a subset of the scikit classifier models, and of all the models tried, RFC has performed the best)
* bear in mind this entire process can take hours to complete.
