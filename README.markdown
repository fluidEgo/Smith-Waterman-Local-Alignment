# Interactive Smith-Waterman Local Alignment

This project provides an interactive web-based implementation of the **Smith-Waterman algorithm** for local sequence alignment using HTML, JavaScript, and p5.js. It is designed for educational purposes, allowing users to step through the matrix computation and traceback process with detailed explanations, visualizations, and accessibility features.

## Features

- **Interactive Interface**: Step through matrix computation and traceback manually or automatically.
- **Detailed Explanations**: Each step displays calculations, including scores for diagonal, up, left, and zero, with directions.
- **Hover Tooltips**: Hover over matrix cells to see how their scores were calculated.
- **Visualizations**: p5.js canvas shows the scoring matrix with highlighted cells and traceback arrows.
- **Accessibility**: ARIA labels, keyboard navigation (Enter for next step, Escape to reset), and high-contrast styling.
- **Progress Bar**: Tracks progress through matrix computation and traceback.
- **Computation Log**: Records all steps, downloadable as a text file.
- **Mode Toggle**: Choose between step-by-step (manual) or automatic computation.
- **Responsive Design**: Works on desktop and mobile devices.

## Prerequisites

- A modern web browser (e.g., Chrome, Firefox, Edge).
- Internet connection to load p5.js via CDN (or local p5.js for offline use).
- Optional: A local web server (e.g., Python's `http.server`) for robust testing.

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/fluidEgo/Smith-Waterman-Local-Alignment.git
   cd Smith-Waterman-Local-Alignment
   ```

2. **File Structure**:
   ```
   Smith-Waterman-Local-Alignment/
   ├── smith-waterman.html  # Main HTML file with the implementation
   ├── README.md            # This file
   └── p5.min.js            # Optional: p5.js library for offline use
   ```

3. **Offline Setup (Optional)**:
   - Download `p5.min.js` from [p5.js](https://p5js.org/download/).
   - Place it in the project folder.
   - Update `smith-waterman.html` to reference the local file:
     ```html
     <script src="p5.min.js"></script>
     ```
     instead of:
     ```html
     <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.2/p5.min.js"></script>
     ```

## Usage

1. **Run the Application**:
   - **Option 1: Open Directly**:
     - Double-click `smith-waterman.html` to open in a web browser.
     - Requires an internet connection for the p5.js CDN unless using the local `p5.min.js`.
   - **Option 2: Use a Local Server**:
     - Run a local server in the project folder:
       ```bash
       python -m http.server 8000
       ```
     - Open `http://localhost:8000/smith-waterman.html` in a browser.

2. **Interacting with the Tool**:
   - **Input Sequences**: Enter two sequences (e.g., "HEAGAWGHEE" and "PAWHEAE").
   - **Set Parameters**: Adjust match score (e.g., 2), mismatch penalty (e.g., -1), and gap penalty (e.g., -2).
   - **Choose Mode**: Select "Step-by-Step" for manual control or "Automatic" for continuous computation (500ms per step).
   - **Start Alignment**: Click "Start Alignment" or press Enter to begin.
   - **Step Through**:
     - In step-by-step mode, click "Next Step" or press Enter to compute each cell or traceback step.
     - In automatic mode, steps proceed automatically.
   - **View Details**:
     - Hover over matrix cells to see calculation details.
     - Check the computation log for a record of all steps.
     - The canvas visualizes the matrix with yellow (current cell) and green (traceback path) highlights, plus red arrows for traceback directions.
   - **Download Log**: Click "Download Log" to save the computation log as a text file.
   - **Reset**: Click "Reset" or press Escape to clear and start over.

3. **Understanding the Output**:
   - **Matrix Computation**: Each step shows the cell being computed, scores (diagonal, up, left, zero), chosen direction, and updates to the maximum score.
   - **Traceback**: Shows the path taken, characters/gaps added, and the evolving alignment.
   - **Final Result**: Displays the aligned sequences and their score.

## Accessibility Features

- **ARIA Labels**: Descriptive labels for screen readers on all interactive elements.
- **Keyboard Navigation**: Press Enter to advance steps, Escape to reset.
- **High-Contrast Styling**: Clear colors and borders for better visibility.
- **Responsive Design**: Adapts to various screen sizes.

## Example

**Input**:
- Sequence 1: `HEAGAWGHEE`
- Sequence 2: `PAWHEAE`
- Match Score: `2`
- Mismatch Penalty: `-1`
- Gap Penalty: `-2`

**Output** (after computation and traceback):
- Aligned Sequence 1: `AWGHE`
- Aligned Sequence 2: `AW-HE`
- Score: `8`

## Contributing

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

Please ensure code follows the existing style and includes tests where applicable.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built with [p5.js](https://p5js.org/) for canvas-based visualizations.
- Inspired by the Smith-Waterman algorithm for local sequence alignment.
