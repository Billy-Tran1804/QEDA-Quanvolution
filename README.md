# QEDA-Quanvolution
The project uses RQCs as a data augmentation technique.
Libraries dependency of the project:
keras==3.9.2
matplotlib==3.10.1
numpy==2.2.5
opencv_contrib_python==4.11.0.86
torch==2.7.0
torchvision==0.22.0

Usage: 
*	Initialize data_path and aug_path by changing the name of the last argument to the datasets to your liking. Note:
**	data_path is the path to the original dataset, so you should take the name from the folder.
**	aug_path is the path to the tensor containing the processed masks from the dataset, so you should take the file with the trailing .pt.
**	Set of dataset and corresponding mask tensor: (processed_CIFAR_10, nearly_completed_transformed_dataset.pt) for the original dataset, and (sub_processed_CIFAR_10, sub_transformed_dataset.pt) for the subset (100 images for each class) for testing runnability.
* Run the main_script.py in the script with arguments, and everything else will follow.

Running arguments:
* epochs (def=100)
* batch_size(def=100)
* beta(def=1.0): The beta value of the beta distribution in the numpy library, used to determine the bounding box.
* p(def=0): The probability of the augmentation being activated in a batch
* quantum (if written, then True): Determine whether QuantumSaliency or Saliency is being used.
*	save_name: The leading name of the outputs, containing the model and its state_dict of the best epoch based on accuracy, the history training, and the training plot. The saved.
  
Examples: These are the corresponding commands in the  terminal for each case:
Baseline: python main_script.py --epochs 100  --save_name basline_run  
Saliency: python main_script.py --epochs 100  --p 0.5 --save_name saliencymix_run  
Quantum:  python main_script.py --epochs 100  --p 0.5 quantum --save_name quantum_run  
Drawback: Still using the same log.txt file for the whole training process, meaning that many runs can have the same file.
