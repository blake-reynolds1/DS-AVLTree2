# AVL Trees Part 3: Deletion
## Objectives
* Definition
* Implementation
* Insertion algorithm
* Deletion algorithm
* Performance
## Delete a Node in AVL Tree
* We have learned how to delete a node in a BST
* In an AVL tree, we do
  - First delete a node, similar as in a BST
  - If AVL feature is not satisfied, try to balance the tree
    - How to handle imbalance is similar as insertion
    - After deletion if the shorter subtree becomes even shorter, balance is needed
    - Apply single rotation or double rotation
      - If it's a left-right or right-left unbalance: double rotation
* <img width="658" alt="Screen Shot 2022-06-28 at 5 07 23 PM" src="https://user-images.githubusercontent.com/89602311/176308611-bdcb19d3-2c66-42e2-a06b-072bfee1fbdf.png">
* <img width="612" alt="Screen Shot 2022-06-28 at 5 07 36 PM" src="https://user-images.githubusercontent.com/89602311/176308658-7c466344-40a9-4fa9-a19f-6932d80e4bd4.png">
* <img width="642" alt="Screen Shot 2022-06-28 at 5 07 52 PM" src="https://user-images.githubusercontent.com/89602311/176308756-0b34195c-b85c-4e59-a16d-62bbe91b143c.png">
* <img width="657" alt="Screen Shot 2022-06-28 at 5 08 03 PM" src="https://user-images.githubusercontent.com/89602311/176308813-1e986829-3292-4880-8844-ddbaf80c1f8f.png">
* 3 key points: 
  - Do insertion or deletion systematically: follow the idea of recursion
  - Remember when to use single or double rotations
  - For deletion, if a node to delete has two children, need to find its immefiate predecessor / successor
## The Height of An AVL Tree
* It is very difficult to estimate the expected height of AVL trees
* The worst-case behavior of AVL trees is essentially no worse than the behavior of random search trees
  - The sparsest possible AVL tree with n nodes has height about 1.44 log n
  - AVL trees are guaranteed to take no more than about 44 percent more time than the optimum
* Empirical evidence suggests that the average behavior of AVL trees is much better than that of random trees
  - Almost as good as perfectly balanced tree
  - Perhaps as small as log n + 0.25
## Self Test
* 1. Delete 20
  - <img width="419" alt="Screen Shot 2022-06-28 at 5 12 41 PM" src="https://user-images.githubusercontent.com/89602311/176310418-6ab553f0-2705-40a5-9f6f-b0689590b5d9.png">
* 1. Answer to delete 20
  - <img width="411" alt="Screen Shot 2022-06-28 at 5 13 05 PM" src="https://user-images.githubusercontent.com/89602311/176310529-dba70eaa-6cda-42eb-be39-a0a14753938a.png">
* 2. Delete 50
  - <img width="394" alt="Screen Shot 2022-06-28 at 5 13 20 PM" src="https://user-images.githubusercontent.com/89602311/176310622-09065d5b-e6a3-457c-8b0d-096a12322321.png">
* 2. Answer to delete 50
  - <img width="427" alt="Screen Shot 2022-06-28 at 5 13 41 PM" src="https://user-images.githubusercontent.com/89602311/176310745-99244efc-98ff-449f-81cd-ec08ede6c90e.png">
* 3. Delete p (use the immediate predecessor)
  - <img width="524" alt="Screen Shot 2022-06-28 at 5 14 11 PM" src="https://user-images.githubusercontent.com/89602311/176310920-148fabeb-2ca7-4c69-8c4f-2b60f992335f.png">
* 3. Answer
  - <img width="521" alt="Screen Shot 2022-06-28 at 5 14 26 PM" src="https://user-images.githubusercontent.com/89602311/176311014-07c37316-100b-40ae-a0eb-3dc0759f782b.png">
# AVL Trees Part 4: Implementation
## Objectives
* Definition
* Implementation
* Insertion algorithm
* Deletion algorithm
* Performance
## Insert
* <img width="632" alt="Screen Shot 2022-06-28 at 5 17 21 PM" src="https://user-images.githubusercontent.com/89602311/176312074-4a0b74d3-f498-49a9-8b55-a8704246f623.png">
* <img width="451" alt="Screen Shot 2022-06-28 at 5 17 55 PM" src="https://user-images.githubusercontent.com/89602311/176312281-5abbb176-b65e-4af0-9ee7-35f5232d3a7a.png">
* <img width="460" alt="Screen Shot 2022-06-28 at 5 18 09 PM" src="https://user-images.githubusercontent.com/89602311/176312364-28612c17-b22a-453d-bf11-5566ee8bbbfe.png">
* <img width="472" alt="Screen Shot 2022-06-28 at 5 18 29 PM" src="https://user-images.githubusercontent.com/89602311/176312482-da2223aa-0baf-403f-994b-fd8bbff26770.png">
* <img width="448" alt="Screen Shot 2022-06-28 at 5 18 56 PM" src="https://user-images.githubusercontent.com/89602311/176312671-f6486acd-8175-45a1-8927-cea7c6998338.png">
* <img width="471" alt="Screen Shot 2022-06-28 at 5 19 14 PM" src="https://user-images.githubusercontent.com/89602311/176312780-d1bd18b9-e3b6-4b97-92df-76aaba84bca1.png">
* <img width="455" alt="Screen Shot 2022-06-28 at 5 19 28 PM" src="https://user-images.githubusercontent.com/89602311/176312862-36bf6086-dcc1-4931-b55a-c350e52a189b.png">
## Delete 
* Rotation is needed when
  - The shorter subtree becomes even shorter
* How to fix
  - Maintain a bool variable named shorter
  - Shorter + balance factor -> try to tell which case it is? -> decide whether a single rotation or a double rotation
