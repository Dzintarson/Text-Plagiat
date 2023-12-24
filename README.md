# Text-Plagiat
Analis text
# Code for Text Plagiarism Analyzer
from difflib import SequenceMatcher

def calculate_similarity(text1, text2):
    # Calculate the similarity ratio using SequenceMatcher
    similarity_ratio = SequenceMatcher(None, text1, text2).ratio()
    return similarity_ratio

def plagiarism_check(text1, text2, threshold=0.8):
    # Check if the similarity ratio exceeds the threshold
    similarity_ratio = calculate_similarity(text1, text2)
    if similarity_ratio >= threshold:
        return True
    else:
        return False

# Example usage
text1 = "This is a sample text for testing."
text2 = "This is a test text for sample."

if plagiarism_check(text1, text2):
    print("Plagiarism detected!")
else:
    print("No plagiarism found.")
