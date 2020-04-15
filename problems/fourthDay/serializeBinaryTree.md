# 题目地址

[https://leetcode-cn.com/problems/xu-lie-hua-er-cha-shu-lcof/](https://leetcode-cn.com/problems/xu-lie-hua-er-cha-shu-lcof/)

# 题目描述
请实现两个函数，分别用来序列化和反序列化二叉树。

示例: 

你可以将以下二叉树：

    1
   / \
  2   3
     / \
    4   5

序列化为 "[1,2,3,null,null,4,5]"

# 思路
广度优先遍历
# 关键点分析
数据处理
# 代码
C++

    class Codec {
    public:

        // Encodes a tree to a single string.
        string serialize(TreeNode* root) {
            string res = "\"[";
            queue<TreeNode*> q;
            if(root) q.push(root);
            while(!q.empty()){
                TreeNode* cur = q.front();
                q.pop();
                if(cur) {
                    q.push(cur->left);
                    q.push(cur->right);
                    res += to_string(cur->val) + ',';
                } else {
                    res += "null,";
                }
            }
            if(!res.empty()) res.pop_back();
            res += "]\"";
            return res;
            
        }

        // Decodes your encoded data to tree.
        TreeNode* deserialize(string data) {
            if(data == "\"]\"") return NULL;
            data = data.substr(2, data.size()-4);
            stringstream ss(data);
            string number;

            getline(ss, number, ',');
            //cout<<data<<endl;
            TreeNode* head = new TreeNode(stoi(number));
            queue<TreeNode*> q;
            q.push(head);
            while(!q.empty()) {
                TreeNode* tmp = q.front();
                q.pop();
                if(getline(ss, number, ',') && number!="null") {
                    TreeNode* temp = new TreeNode(stoi(number));
                    tmp->left = temp;
                    q.push(temp);
                }
                if(getline(ss, number, ',') && number!="null") {
                    TreeNode* temp = new TreeNode(stoi(number));
                    tmp->right = temp;
                    q.push(temp);
                }
            }
            return head;
        }

    };

## [返回题目列表](../../README.md)