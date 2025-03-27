# Autocomplete and Phonetic Matching Program

This C++ program implements an autocomplete feature with phonetic matching and abbreviation conversion. It uses a Trie data structure for efficient word storage and retrieval, along with functionalities to customize the dictionary and convert abbreviations to their full forms.

## Key Features

-   **Autocomplete:** Suggests possible words based on a given prefix using a Trie data structure.
-   **Phonetic Matching:** Provides suggestions for words that sound similar to the input word.
-   **Abbreviation Conversion:** Automatically converts abbreviations in a sentence to their full forms.
-   **Customizable Dictionary:** Allows users to add new words to the dictionary.
-   **Dictionary Management:** Enables loading a new dictionary from a file, viewing the current dictionary, and deleting words.
-   **Menu-Driven Interface:** Offers a user-friendly menu for easy interaction with the program.

## Installation

To use this program, you need a C++ compiler (e.g., g++) and the standard C++ library.

1.  Clone the repository to your local machine.
2.  Compile the `main.cpp` file along with the required data files (`dictionary.txt`, `abbreviations.txt`, and `phonetic.txt`).


## Usage

After compiling the code, run the executable. The program presents a menu with various options.


### Data Files

The program uses the following data files:

-   `dictionary.txt`: Contains a list of words used for autocomplete suggestions.
-   `abbreviations.txt`: Contains a list of abbreviations and their full forms. Each line should have the format "abbreviation full form".
-   `phonetic.txt`: Contains words that sound alike, separated by commas. Each line represents a group of phonetically similar words.


### Menu Options

1.  **Autocomplete:** Enter a prefix to get word suggestions.
2.  **Phonetic Matching:** Enter a word to find phonetically similar words.
3.  **Auto convert abbreviation:** Enter a sentence with abbreviations to convert them to their full forms.
4.  **Customize dictionary:** Add a new word to the dictionary.
5.  **Load new dictionary:** Load words from a file into the dictionary.
6.  **View dictionary:** Display all the words in the current dictionary.
7.  **Delete word:** Remove a word from the dictionary.
8.  **Help:** Display the help menu.
9.  **Exit:** Exit the program.

## Code Structure

The project consists of the following files:

-   `main.cpp`: Contains the main function, the `CompressedTrie` class, and related functions.
-   `dictionary.txt`: Contains the dictionary words.
-   `abbreviations.txt`: Contains abbreviations and their full forms.
-   `phonetic.txt`: Contains words that sound alike.

### Classes and Methods

#### TrieNode Structure

-   `vector> children`: A vector of unique pointers to child `TrieNode` objects, representing the next possible characters in words.
-   `bool isEndOfWord`: A flag indicating if the node represents the end of a valid word.
-   `int frequency`: The frequency of the word in the dictionary.
-   `string word`: The complete word represented by the node.

#### CompressedTrie Class

-   `CompressedTrie()`: Constructor that loads the dictionary, abbreviations, and phonetic mappings from files.
-   `void autocomplete(const string& prefix)`: Provides autocomplete suggestions for the given prefix.
-   `void customizeDictionary(const string& word)`: Adds a new word to the dictionary.
-   `void phoneticAutocomplete(const string& word)`: Finds and displays phonetically similar words.
-   `void autoConvertAbbreviation(string& sentence)`: Converts abbreviations in a sentence to their full forms.
-   `void loadNewDictionary(const string& filepath)`: Loads words from a specified file into the dictionary.
-   `void viewDictionary()`: Displays all words in the dictionary.
-   `void deleteWord(const string& word)`: Removes a word from the dictionary.
-   `void displayHelp()`: Displays the help menu.

#### Private Methods

-   `void insertWord(TrieNode* node, const string& word, int freq = 1)`: Inserts a word into the Trie.
-   `void loadDictionary()`: Loads words from `dictionary.txt` into the Trie.
-   `void loadAbbreviations()`: Loads abbreviations and their full forms from `abbreviations.txt`.
-   `void loadPhonetics()`: Loads phonetic mappings from `phonetic.txt`.
-   `void getSuggestions(TrieNode* node, vector& suggestions, int limit = 3)`: Retrieves autocomplete suggestions from the Trie.
-   `TrieNode* searchPrefix(TrieNode* node, const string& prefix)`: Searches for the Trie node representing the given prefix.
-   `string getAbbreviation(const string& word)`: Retrieves the full form of an abbreviation.
-   `void displayDictionary(TrieNode* node, string prefix)`: Displays all the words in the dictionary (recursive helper function).
-   `bool removeWord(TrieNode* node, const string& word, int depth = 0)`: Removes a word from the dictionary (recursive helper function).

## Contributing

Contributions are welcome! Please submit pull requests or issues to improve the code.

## License

This project is licensed under the MIT License.


