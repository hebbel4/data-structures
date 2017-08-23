class Trie {
    class TrieNode {
        char val;
        TrieNode[] children = new TrieNode[26];
        boolean isEnd = false;
        public TrieNode (char c) {
            val = c;
        }
    }
    TrieNode root;
    /** Initialize your data structure here. */
    public Trie() {
        root = new TrieNode(' ');
    }

    /** Inserts a word into the trie. */
    public void insert(String word) {
        TrieNode cur = root;
        for (char c : word.toCharArray()) {
            if (cur.children[c - 'a'] == null) {
                cur.children[c - 'a'] = new TrieNode(c);
            }
            cur = cur.children[c - 'a'];
        }
        cur.isEnd = true;
    }

    /** Returns if the word is in the trie. */
    public boolean search(String word) {
        TrieNode cur = root;
        for (char c : word.toCharArray()) {
            if (cur.children[c - 'a'] == null) return false;
            cur = cur.children[c - 'a'];
        }
        return cur.isEnd;
    }

    /** Returns if there is any word in the trie that starts with the given prefix. */
    public boolean startsWith(String prefix) {
        TrieNode cur = root;
        for (char c : prefix.toCharArray()) {
            if (cur.children[c - 'a'] == null) return false;
            cur = cur.children[c - 'a'];
        }
        return true;
    }
}

/* generalized version with hashmap */
class Trie {
    class TrieNode {
        char val;
        HashMap<Character, TrieNode> children = new HashMap<>();
        boolean isEnd = false;
        public TrieNode (char c) {
            val = c;
        }
    }
    TrieNode root;
    /** Initialize your data structure here. */
    public Trie() {
        root = new TrieNode(' ');
    }

    /** Inserts a word into the trie. */
    public void insert(String word) {
        TrieNode cur = root;
        for (char c : word.toCharArray()) {
            if (!cur.children.containsKey(c)) {
                cur.children.put(c, new TrieNode(c));
            }
            cur = cur.children.get(c);
        }
        cur.isEnd = true;
    }

    /** Returns if the word is in the trie. */
    public boolean search(String word) {
        TrieNode cur = root;
        for (char c : word.toCharArray()) {
            if (!cur.children.containsKey(c)) return false;
            cur = cur.children.get(c);
        }
        return cur.isEnd;
    }

    /** Returns if there is any word in the trie that starts with the given prefix. */
    public boolean startsWith(String prefix) {
        TrieNode cur = root;
        for (char c : prefix.toCharArray()) {
            if (!cur.children.containsKey(c)) return false;
            cur = cur.children.get(c);
        }
        return true;
    }

    public void delete(String word) {
        return delete(root, word, index);
    }

    private boolean delete(TrieNode cur, String word, int index) {
        if (index == word.length()) {
            if (!cur.isEnd) return false;
            cur.isEnd = false;
            return cur.children.size() == 0;
        }
        char c = word.charAt(index);
        if (!cur.children.containsKey(c)) return false;
        boolean isDelete = delete(cur.children.get(c), word, index + 1);
        if (isDelete) {
            cur.children.remove(c);
            return cur.children.size() == 0;
        }
        return false;
    }
}