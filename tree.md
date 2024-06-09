### Building Expression Tree

```c
BTreeNode* MakeExpTree(char* exp, int len){
    Stack stack;
    BTreeNode * node, *right_node, *left_node;

    InitStack(&stack);
    for(int i=0;i<len;i++){
        if('0'<exp[i] && exp[i]<'9'){
            node = CreateNode(exp[i]);
        }
        else{
            right_node = Peek(&stack), Pop(&stack);
            left_node = Peek(&stack), Pop(&stack);

            node = CreateNode(exp[i]);
            CreateRightSubtree(node, right_node);
            CreateLeftSubtree(node, left_node);
        }
        Push(&stack, node);
    }
    return Peek(&stack);
}```