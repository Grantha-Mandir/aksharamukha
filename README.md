http://aksharamukha.appspot.com

Aksharamukha aims to provide transliteration a.k.a script conversion between various scripts within the Indic cultural sphere.  Apart from the simple mapping of characters, Askharamukha also attempts to implement various script/language-specific orthographic conventions (where known) such as vowel lengths, gemination and nasalization. It also provides several customization options to fine-tune and get the desired orthography.

It is a total rewrite of the PHP-based version available [here](https://launchpad.net/aksharamukha) and [here](https://github.com/nareshv/aksharamukha).

Aksharamukha as of now supports 66 scripts and 8 romanization methods.

## Front End
The front end is written using Quasar and Vue. Use _npm install_ to install all the dependencies and then use _quasar dev_ to start the front end. Also, please point the api to localhost at mixins/ScriptMixin.js.

## Back End
The back end is written in Python 3 with Flask. After installing all the libraries, use _python3 main.py_ to intialize the backend server.

## JSON Resource
Frequently used script resouces have been made available as JSON file under aksharamukha-back/resources.

You can find the overall mapping as a JSON file [here](https://github.com/virtualvinodh/aksharamukha/tree/master/aksharamukha-back/resources/script_mapping). Those characters that have approximate mappings from the generic Indic scheme are marked with 'ʽ' (U+02BD). For instance, Thaana (Dhivehi) does not have /ga/, which have been approximated to /ka/. You may want to remove the character as part of post-processing. Same with Phags-Pa, /Ṿ/ was extraneously added to differentiate vowels, vowel-signs and aspirate-markers. You have to remove that character as well after the mapping has been done.

The Script Matrix data is available [here](https://github.com/virtualvinodh/aksharamukha/tree/master/aksharamukha-back/resources/script_matrix). The file suffix indicates the guiding romanization and the how the characters have been divided into chunks. << script_matrix_IAST5.json >> indicates that the guiding script is IAST and the characters have been divided into chunks of 5.

The syllabary for each script can be found [here](https://github.com/virtualvinodh/aksharamukha/tree/master/aksharamukha-back/resources/syllabary). The file includes the list of vowels, consonants and the complete consonant-vowel compounds for each script.

The list of all possible Sanskrit (and Pali) conjuncts for each script can be found [here](https://github.com/virtualvinodh/aksharamukha/tree/master/aksharamukha-back/resources/conjuncts1) and [here](https://github.com/virtualvinodh/aksharamukha/tree/master/aksharamukha-back/resources/conjuncts2) . The file includes the list of vowels, consonants and the complete consonant-vowel compounds for each script. (The folder had to be split due to Google App Engine limitations). The suffix indicates the appended vowel. For instance, << conjuncts_Gujarati_o.json >> indicated all the possible gujarati conjuncts that occurs with the vowel /o/.

The list of common letters between two scriptscan be found [here](https://github.com/virtualvinodh/aksharamukha/tree/master/aksharamukha-back/resources/common_letters1), [here](https://github.com/virtualvinodh/aksharamukha/tree/master/aksharamukha-back/resources/common_letters2) and [here](https://github.com/virtualvinodh/aksharamukha/tree/master/aksharamukha-back/resources/common_letters3). (The folder had to be split due to Google App Engine limitations as above).

The project is released under GNU AGPL 3.0 License