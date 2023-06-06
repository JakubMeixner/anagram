# anagram
def is_anagram(word1, word2):
    if len(word1) != len(word2):
        return False

    count = [0] * 26  # Assuming only lowercase alphabets
    for char in word1:
        count[ord(char) - ord('a')] += 1

    for char in word2:
        count[ord(char) - ord('a')] -= 1
        if count[ord(char) - ord('a')] < 0:
            return False

    return True

def find_anagrams(word, words_list):
    anagrams = []
    for w in words_list:
        if is_anagram(word, w):
            anagrams.append(w)

    return anagrams
