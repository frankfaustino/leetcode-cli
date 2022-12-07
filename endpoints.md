# LeetCode Endpoints

## Authentication

### Login

```json
// HTTP POST to https://leetcode.com/accounts/login/
{
    "login": "username",
    "password": "password",
    "csrfmiddlewaretoken": "CSRF_TOKEN"
}
```

### Note

```plaintext
# Grab csrftoken and LEETCODE_SESSION from cookies for subsequent API calls
```

## Daily Challenge

### GraphQL Query

```gql
# HTTP POST to https://leetcode.com/graphql
query questionOfToday {
    activeDailyCodingChallengeQuestion {
        date
        userStatus
        link
        question {
            acRate
            difficulty
            freqBar
            frontendQuestionId: questionFrontendId
            isFavor
            paidOnly: isPaidOnly
            status
            title
            titleSlug
            hasVideoSolution
            hasSolution
            topicTags {
                name
                id
                slug
            }
        }
    }
}
```

### cURL Request

```sh
curl --request POST \
  --url https://leetcode.com/graphql \
  --header 'Content-Type: application/json' \
  --data '{"query":"query questionOfToday {\n\tactiveDailyCodingChallengeQuestion {\n\t\tdate\n\t\tuserStatus\n\t\tlink\n\t\tquestion {\n\t\t\tacRate\n\t\t\tdifficulty\n\t\t\tfreqBar\n\t\t\tfrontendQuestionId: questionFrontendId\n\t\t\tisFavor\n\t\t\tpaidOnly: isPaidOnly\n\t\t\tstatus\n\t\t\ttitle\n\t\t\ttitleSlug\n\t\t\thasVideoSolution\n\t\t\thasSolution\n\t\t\ttopicTags {\n\t\t\t\tname\n\t\t\t\tid\n\t\t\t\tslug\n\t\t\t}\n\t\t}\n\t}\n}\n","operationName":"questionOfToday"}'
```

### Response

```json
{
    "data": {
        "activeDailyCodingChallengeQuestion": {
            "date": "2022-12-07",
            "userStatus": "NotStart",
            "link": "/problems/range-sum-of-bst/",
            "question": {
                "acRate": 85.79967214784836,
                "difficulty": "Easy",
                "freqBar": null,
                "frontendQuestionId": "938",
                "isFavor": false,
                "paidOnly": false,
                "status": null,
                "title": "Range Sum of BST",
                "titleSlug": "range-sum-of-bst",
                "hasVideoSolution": true,
                "hasSolution": true,
                "topicTags": [
                    {
                        "name": "Tree",
                        "id": "VG9waWNUYWdOb2RlOjIw",
                        "slug": "tree"
                    },
                    {
                        "name": "Depth-First Search",
                        "id": "VG9waWNUYWdOb2RlOjIx",
                        "slug": "depth-first-search"
                    },
                    {
                        "name": "Binary Search Tree",
                        "id": "VG9waWNUYWdOb2RlOjMw",
                        "slug": "binary-search-tree"
                    },
                    {
                        "name": "Binary Tree",
                        "id": "VG9waWNUYWdOb2RlOjYxMDU3",
                        "slug": "binary-tree"
                    }
                ]
            }
        }
    }
}
```
