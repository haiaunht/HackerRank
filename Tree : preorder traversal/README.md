# [Tree: preorder traversal]

```
  public static void preOrder(Node root) {
        if (root == null) return;

        System.out.print(root.data + " ");
        if (root.left != null) preOrder(root.left);
        if (root.right != null) preOrder(root.right);
    }

```
