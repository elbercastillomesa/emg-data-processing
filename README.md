# emg-data-processing

This project intends the implementation of a system for acquisition, processing and classification of EMG signals from the forearm with the ability to identify six movements of the metacarpal joint and
control an electromechanical clamp with three degrees of freedom. 

This is a repetition of the work already achieved on 2016, please refer to [Undergraduate Project](https://psi.univalle.edu.co) for academic details.

---

### **Step 1: Signal Acquisition**
- **Input Data:**
  - Import your EMG data from text files into Python using libraries like `numpy` or `pandas`.
  - Ensure the data is properly formatted (e.g., columns for time, amplitude, or frequency, if applicable).
- **Preprocessing:**
  - Filter the signals to remove noise using bandpass filters (common EMG frequencies are between 20 Hz and 500 Hz). Use libraries like `scipy` or `biosppy` for this.
  - Normalize the signals to standardize the amplitude range for consistency.
- **Visualization:**
  - Plot the raw and filtered signals using `matplotlib` or `seaborn` to inspect their quality.

---

### **Step 2: Feature Extraction**
- **Extract Discriminant Features:**
  - Common features for EMG include:
    - **Time-domain:** Mean Absolute Value (MAV), Root Mean Square (RMS), Zero Crossing (ZC), Slope Sign Changes (SSC).
    - **Frequency-domain:** Power Spectrum Density (PSD), Median Frequency.
    - Use `numpy` or `scipy` for these computations.
  - Organize these features into a structured dataset (e.g., a dataframe) for training the classifier.

---

### **Step 3: Signal Classification**
- **Select Machine Learning Models:**
  - Start with common classifiers:
    - **Support Vector Machines (SVM):** Good for small datasets.
    - **Random Forest:** Robust with noisy features.
    - **K-Nearest Neighbors (KNN):** Simple and effective for classification tasks.
    - Use libraries like `scikit-learn`.
- **Train and Evaluate:**
  - Split your dataset into training and testing sets.
  - Train the classifier on the extracted features and test its performance (accuracy, precision, recall).
  - Use metrics like cross-validation and confusion matrices to validate results.

---

### **Step 4: Movement Classification**
- **Define Movements:**
  - Based on the abstract, aim to identify six movements of the metacarpal joint.
  - Assign labels to your data corresponding to the movements (if this isn’t already done).
- **Test Protocol:**
  - Develop a testing protocol to quantify the classifier’s accuracy in identifying movements.
  - Set a baseline target accuracy based on the reported 65.8%.

---

### **Step 5: Control System Design (Optional)**
- If you plan to control an electromechanical clamp:
  - **Signal Mapping:** Map the identified movements to control commands for the clamp.
  - **Communication Protocol:** Use interfaces like Bluetooth, serial communication, or GPIO (e.g., with Raspberry Pi or Arduino).

---

### **Step 6: Python Application Development**
- **Modules to Build:**
  - **Data Loader:** To load and preprocess EMG signals from text files.
  - **Feature Extractor:** To extract discriminant features.
  - **Classifier:** To load the trained model and classify movements.
  - **GUI (Optional):** Use libraries like `tkinter` or `PyQt` for a user interface.
  - **Visualization:** Display real-time signal plots and classification results.

---

### **Step 7: Testing and Deployment**
- **Validation:**
  - Conduct tests on new datasets to ensure generalization.
  - Compare performance with other models and refine features if necessary.
- **Deployment:**
  - Package the application using `PyInstaller` or `cx_Freeze`.
  - Create a user-friendly interface for loading signals and displaying results.

---

### Recommended Libraries
1. **Data Handling & Preprocessing:**
   - `numpy`, `pandas`, `scipy`
2. **Signal Processing:**
   - `biosppy`, `pywavelets`
3. **Machine Learning:**
   - `scikit-learn`, `tensorflow` (if deep learning is considered)
4. **Visualization:**
   - `matplotlib`, `seaborn`
5. **GUI Development (Optional):**
   - `tkinter`, `PyQt`, `Dash`