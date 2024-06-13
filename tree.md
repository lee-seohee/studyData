### Building Expression Tree

```c
BTreeNode* MakeExpTree(char* exp, int len){
    Stack stack; //stack은 FILO
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

### Inorder in Threaded Binary Tree //Inorder == LCR

```c
BTreeNode* leftMost(BTreeNode* node){
    if(node == NULL) return NULL;
    while(node -> left_chile != NULL)
        node = node -> left_child;
    
    return node;
}

void InOrder(BTreeNode* node){
    BTreeNode* cur = leftmost(node);
    while(cur != NULL){
        printf("%d", cur->item);
    if(cur -> isTheaded) //스레드면 right_child로 이동
        cur = cur -> right_child;
    else
        cur = leftmost(cur -> right_child); //그렇지 않으면 right_child의 가장 왼쪽으로 이동
    }
}
```