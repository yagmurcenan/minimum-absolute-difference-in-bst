# minimum-absolute-difference-in-bst
class Solution {

    private int prev = -100000;
    private int min = 100000;

    public int getMinimumDifference(TreeNode node) {
        if (node == null) return min;

        getMinimumDifference(node.left);

        if (prev != -100000) {
            min = Math.min(min, node.val - prev);
        }
        prev = node.val;

        getMinimumDifference(node.right);

        return min;
    }
}
