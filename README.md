# Navigation Task

## Create a Javascript project with two files:

- main.js
- utils.js

## The ***utils.js*** should contain a function to:

- build navigation data structure
- fetch the raw navigation list from the Strapi API using **fetch**
  - The endpoint is [http://172.20.91.21:85/navigations](http://172.20.91.21:85/navigations)

## The ***main.js*** should call the functions in the utils:

- Fetch the data from the API and store it in a variable called **rawData**
- Process the rawData by passing it in the build navigation data structure and storing the return value in a variable
  called **finalNavigationList**

## A Sample Response Data

```json
[
  {
    "id": 1,
    "title": "Intro",
    "url": "/intro",
    "published_at": "2021-12-01T11:35:47.000Z",
    "created_at": "2021-12-01T11:29:48.000Z",
    "updated_at": "2021-12-01T11:45:09.000Z",
    "navigation": null,
    "parent": null,
    "page": {
      "id": 1,
      "Title": "intro",
      "published_at": "2021-12-01T10:33:25.000Z",
      "created_at": "2021-12-01T10:27:40.000Z",
      "updated_at": "2021-12-01T11:49:06.000Z",
      "page_zone": [
        {
          "__component": "page.rich-text",
          "id": 1,
          "Richtext": "## This is a test Image\n![The First Step.png](/uploads/The_First_Step_79bc575429.png)\n"
        }
      ]
    }
  },
  {
    "id": 2,
    "title": "Messaging",
    "url": "/messaging",
    "published_at": "2021-12-01T11:35:59.000Z",
    "created_at": "2021-12-01T11:30:15.000Z",
    "updated_at": "2021-12-02T15:10:03.000Z",
    "navigation": null,
    "parent": null,
    "page": null
  },
  {
    "id": 3,
    "title": "Message Category",
    "url": "/category",
    "published_at": "2021-12-01T11:35:55.000Z",
    "created_at": "2021-12-01T11:32:36.000Z",
    "updated_at": "2021-12-01T11:45:46.000Z",
    "navigation": 2,
    "parent": {
      "id": 2,
      "title": "Messaging",
      "url": "/messaging",
      "published_at": "2021-12-01T11:35:59.000Z",
      "created_at": "2021-12-01T11:30:15.000Z",
      "updated_at": "2021-12-02T15:10:03.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": {
      "id": 2,
      "Title": "Message Category",
      "published_at": "2021-12-01T10:33:30.000Z",
      "created_at": "2021-12-01T10:28:04.000Z",
      "updated_at": "2021-12-01T10:33:30.000Z",
      "page_zone": []
    }
  },
  {
    "id": 4,
    "title": "Bulk Messaging",
    "url": "/bulk",
    "published_at": "2021-12-01T11:35:27.000Z",
    "created_at": "2021-12-01T11:34:09.000Z",
    "updated_at": "2021-12-01T11:39:23.000Z",
    "navigation": 2,
    "parent": {
      "id": 2,
      "title": "Messaging",
      "url": "/messaging",
      "published_at": "2021-12-01T11:35:59.000Z",
      "created_at": "2021-12-01T11:30:15.000Z",
      "updated_at": "2021-12-02T15:10:03.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": null
  },
  {
    "id": 5,
    "title": "Compose SMS with contact file",
    "url": "/compose-sms-with-contacts-file",
    "published_at": "2021-12-01T11:35:36.000Z",
    "created_at": "2021-12-01T11:35:12.000Z",
    "updated_at": "2021-12-01T12:31:15.000Z",
    "navigation": 4,
    "parent": {
      "id": 4,
      "title": "Bulk Messaging",
      "url": "/bulk",
      "published_at": "2021-12-01T11:35:27.000Z",
      "created_at": "2021-12-01T11:34:09.000Z",
      "updated_at": "2021-12-01T11:39:23.000Z",
      "navigation": 2,
      "parent": 2,
      "page": null
    },
    "page": {
      "id": 3,
      "Title": "Compose SMS with Contact File",
      "published_at": "2021-12-01T10:33:21.000Z",
      "created_at": "2021-12-01T10:28:22.000Z",
      "updated_at": "2021-12-01T10:33:21.000Z",
      "page_zone": []
    }
  },
  {
    "id": 6,
    "title": "Send SMS from file",
    "url": "/send-sms-from-file",
    "published_at": "2021-12-01T12:31:47.000Z",
    "created_at": "2021-12-01T12:31:01.000Z",
    "updated_at": "2021-12-01T12:31:47.000Z",
    "navigation": null,
    "parent": {
      "id": 4,
      "title": "Bulk Messaging",
      "url": "/bulk",
      "published_at": "2021-12-01T11:35:27.000Z",
      "created_at": "2021-12-01T11:34:09.000Z",
      "updated_at": "2021-12-01T11:39:23.000Z",
      "navigation": 2,
      "parent": 2,
      "page": null
    },
    "page": {
      "id": 4,
      "Title": "Send SMS from file",
      "published_at": "2021-12-01T10:33:38.000Z",
      "created_at": "2021-12-01T10:29:20.000Z",
      "updated_at": "2021-12-01T10:33:38.000Z",
      "page_zone": []
    }
  },
  {
    "id": 7,
    "title": "DND",
    "url": "/dnd",
    "published_at": "2021-12-01T12:32:21.000Z",
    "created_at": "2021-12-01T12:32:15.000Z",
    "updated_at": "2021-12-01T12:32:21.000Z",
    "navigation": null,
    "parent": {
      "id": 2,
      "title": "Messaging",
      "url": "/messaging",
      "published_at": "2021-12-01T11:35:59.000Z",
      "created_at": "2021-12-01T11:30:15.000Z",
      "updated_at": "2021-12-02T15:10:03.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": null
  },
  {
    "id": 8,
    "title": "Add Single member to DND",
    "url": "/add-single-member-to-dnd",
    "published_at": "2021-12-01T12:33:21.000Z",
    "created_at": "2021-12-01T12:33:17.000Z",
    "updated_at": "2021-12-01T12:33:21.000Z",
    "navigation": null,
    "parent": {
      "id": 7,
      "title": "DND",
      "url": "/dnd",
      "published_at": "2021-12-01T12:32:21.000Z",
      "created_at": "2021-12-01T12:32:15.000Z",
      "updated_at": "2021-12-01T12:32:21.000Z",
      "navigation": null,
      "parent": 2,
      "page": null
    },
    "page": {
      "id": 5,
      "Title": "Add single meber to DND",
      "published_at": "2021-12-01T10:33:00.000Z",
      "created_at": "2021-12-01T10:29:53.000Z",
      "updated_at": "2021-12-01T10:33:00.000Z",
      "page_zone": []
    }
  },
  {
    "id": 9,
    "title": "Bulk add to DND",
    "url": "/bulk-add-to-dnd",
    "published_at": "2021-12-01T12:34:22.000Z",
    "created_at": "2021-12-01T12:34:12.000Z",
    "updated_at": "2021-12-01T12:34:22.000Z",
    "navigation": null,
    "parent": {
      "id": 7,
      "title": "DND",
      "url": "/dnd",
      "published_at": "2021-12-01T12:32:21.000Z",
      "created_at": "2021-12-01T12:32:15.000Z",
      "updated_at": "2021-12-01T12:32:21.000Z",
      "navigation": null,
      "parent": 2,
      "page": null
    },
    "page": {
      "id": 6,
      "Title": "Bulk Add to DND",
      "published_at": "2021-12-01T10:33:11.000Z",
      "created_at": "2021-12-01T10:30:06.000Z",
      "updated_at": "2021-12-01T10:33:11.000Z",
      "page_zone": []
    }
  },
  {
    "id": 10,
    "title": "Logs",
    "url": "/logs",
    "published_at": "2021-12-01T12:34:58.000Z",
    "created_at": "2021-12-01T12:34:55.000Z",
    "updated_at": "2021-12-01T12:34:58.000Z",
    "navigation": null,
    "parent": {
      "id": 2,
      "title": "Messaging",
      "url": "/messaging",
      "published_at": "2021-12-01T11:35:59.000Z",
      "created_at": "2021-12-01T11:30:15.000Z",
      "updated_at": "2021-12-02T15:10:03.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": {
      "id": 7,
      "Title": "Report",
      "published_at": "2021-12-01T10:33:33.000Z",
      "created_at": "2021-12-01T10:30:16.000Z",
      "updated_at": "2021-12-01T10:33:34.000Z",
      "page_zone": []
    }
  },
  {
    "id": 11,
    "title": "Member Register",
    "url": "/member-register",
    "published_at": "2021-12-01T12:36:16.000Z",
    "created_at": "2021-12-01T12:35:47.000Z",
    "updated_at": "2021-12-01T12:36:16.000Z",
    "navigation": null,
    "parent": null,
    "page": null
  },
  {
    "id": 12,
    "title": "Bulk Register",
    "url": "/bulk-register",
    "published_at": "2021-12-01T12:38:50.000Z",
    "created_at": "2021-12-01T12:37:06.000Z",
    "updated_at": "2021-12-01T12:38:50.000Z",
    "navigation": null,
    "parent": {
      "id": 11,
      "title": "Member Register",
      "url": "/member-register",
      "published_at": "2021-12-01T12:36:16.000Z",
      "created_at": "2021-12-01T12:35:47.000Z",
      "updated_at": "2021-12-01T12:36:16.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": null
  },
  {
    "id": 13,
    "title": "Whitelist",
    "url": "/whitelist",
    "published_at": "2021-12-01T12:39:00.000Z",
    "created_at": "2021-12-01T12:37:49.000Z",
    "updated_at": "2021-12-01T12:39:00.000Z",
    "navigation": null,
    "parent": {
      "id": 12,
      "title": "Bulk Register",
      "url": "/bulk-register",
      "published_at": "2021-12-01T12:38:50.000Z",
      "created_at": "2021-12-01T12:37:06.000Z",
      "updated_at": "2021-12-01T12:38:50.000Z",
      "navigation": null,
      "parent": 11,
      "page": null
    },
    "page": {
      "id": 8,
      "Title": "Whitelist B",
      "published_at": "2021-12-01T10:33:49.000Z",
      "created_at": "2021-12-01T10:30:32.000Z",
      "updated_at": "2021-12-01T10:33:49.000Z",
      "page_zone": []
    }
  },
  {
    "id": 14,
    "title": "Blacklist",
    "url": "/blacklist",
    "published_at": "2021-12-01T12:38:43.000Z",
    "created_at": "2021-12-01T12:38:37.000Z",
    "updated_at": "2021-12-01T12:38:43.000Z",
    "navigation": null,
    "parent": {
      "id": 12,
      "title": "Bulk Register",
      "url": "/bulk-register",
      "published_at": "2021-12-01T12:38:50.000Z",
      "created_at": "2021-12-01T12:37:06.000Z",
      "updated_at": "2021-12-01T12:38:50.000Z",
      "navigation": null,
      "parent": 11,
      "page": null
    },
    "page": {
      "id": 9,
      "Title": "Blacklist B",
      "published_at": "2021-12-01T10:33:04.000Z",
      "created_at": "2021-12-01T10:30:43.000Z",
      "updated_at": "2021-12-01T10:33:04.000Z",
      "page_zone": []
    }
  },
  {
    "id": 15,
    "title": "Single Register",
    "url": "/single-register",
    "published_at": "2021-12-01T12:40:13.000Z",
    "created_at": "2021-12-01T12:40:11.000Z",
    "updated_at": "2021-12-01T12:40:13.000Z",
    "navigation": null,
    "parent": {
      "id": 11,
      "title": "Member Register",
      "url": "/member-register",
      "published_at": "2021-12-01T12:36:16.000Z",
      "created_at": "2021-12-01T12:35:47.000Z",
      "updated_at": "2021-12-01T12:36:16.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": null
  },
  {
    "id": 16,
    "title": "Whitelist",
    "url": "/whitelist",
    "published_at": "2021-12-01T12:46:31.000Z",
    "created_at": "2021-12-01T12:46:25.000Z",
    "updated_at": "2021-12-01T12:46:31.000Z",
    "navigation": null,
    "parent": {
      "id": 15,
      "title": "Single Register",
      "url": "/single-register",
      "published_at": "2021-12-01T12:40:13.000Z",
      "created_at": "2021-12-01T12:40:11.000Z",
      "updated_at": "2021-12-01T12:40:13.000Z",
      "navigation": null,
      "parent": 11,
      "page": null
    },
    "page": {
      "id": 10,
      "Title": "Whitelist S",
      "published_at": "2021-12-01T10:33:54.000Z",
      "created_at": "2021-12-01T10:30:54.000Z",
      "updated_at": "2021-12-01T10:33:54.000Z",
      "page_zone": []
    }
  },
  {
    "id": 17,
    "title": "Blacklist",
    "url": "/blacklist",
    "published_at": "2021-12-01T12:47:23.000Z",
    "created_at": "2021-12-01T12:47:10.000Z",
    "updated_at": "2021-12-01T12:47:23.000Z",
    "navigation": null,
    "parent": {
      "id": 15,
      "title": "Single Register",
      "url": "/single-register",
      "published_at": "2021-12-01T12:40:13.000Z",
      "created_at": "2021-12-01T12:40:11.000Z",
      "updated_at": "2021-12-01T12:40:13.000Z",
      "navigation": null,
      "parent": 11,
      "page": null
    },
    "page": {
      "id": 11,
      "Title": "Blacklist S",
      "published_at": "2021-12-01T10:33:08.000Z",
      "created_at": "2021-12-01T10:31:06.000Z",
      "updated_at": "2021-12-01T10:33:08.000Z",
      "page_zone": []
    }
  },
  {
    "id": 18,
    "title": "Support & changelog",
    "url": "/support-and-changelog",
    "published_at": "2021-12-01T12:48:16.000Z",
    "created_at": "2021-12-01T12:48:07.000Z",
    "updated_at": "2021-12-01T12:48:16.000Z",
    "navigation": null,
    "parent": null,
    "page": null
  },
  {
    "id": 19,
    "title": "changelog",
    "url": "/changelog",
    "published_at": "2021-12-01T12:48:52.000Z",
    "created_at": "2021-12-01T12:48:49.000Z",
    "updated_at": "2021-12-01T12:48:52.000Z",
    "navigation": null,
    "parent": {
      "id": 18,
      "title": "Support & changelog",
      "url": "/support-and-changelog",
      "published_at": "2021-12-01T12:48:16.000Z",
      "created_at": "2021-12-01T12:48:07.000Z",
      "updated_at": "2021-12-01T12:48:16.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": {
      "id": 12,
      "Title": "Changelog",
      "published_at": "2021-12-01T10:33:16.000Z",
      "created_at": "2021-12-01T10:31:21.000Z",
      "updated_at": "2021-12-01T10:33:16.000Z",
      "page_zone": []
    }
  },
  {
    "id": 20,
    "title": "Support",
    "url": "/support",
    "published_at": "2021-12-01T12:49:31.000Z",
    "created_at": "2021-12-01T12:49:29.000Z",
    "updated_at": "2021-12-01T12:49:31.000Z",
    "navigation": null,
    "parent": {
      "id": 18,
      "title": "Support & changelog",
      "url": "/support-and-changelog",
      "published_at": "2021-12-01T12:48:16.000Z",
      "created_at": "2021-12-01T12:48:07.000Z",
      "updated_at": "2021-12-01T12:48:16.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": {
      "id": 13,
      "Title": "Support",
      "published_at": "2021-12-01T10:33:45.000Z",
      "created_at": "2021-12-01T10:31:31.000Z",
      "updated_at": "2021-12-01T10:33:45.000Z",
      "page_zone": []
    }
  },
  {
    "id": 21,
    "title": "USSD",
    "url": "/ussd",
    "published_at": "2021-12-02T13:22:20.000Z",
    "created_at": "2021-12-02T13:22:17.000Z",
    "updated_at": "2021-12-02T13:22:20.000Z",
    "navigation": null,
    "parent": null,
    "page": null
  },
  {
    "id": 22,
    "title": "USSD Logs",
    "url": "/logs",
    "published_at": "2021-12-02T13:24:29.000Z",
    "created_at": "2021-12-02T13:23:36.000Z",
    "updated_at": "2021-12-02T13:24:29.000Z",
    "navigation": null,
    "parent": {
      "id": 21,
      "title": "USSD",
      "url": "/ussd",
      "published_at": "2021-12-02T13:22:20.000Z",
      "created_at": "2021-12-02T13:22:17.000Z",
      "updated_at": "2021-12-02T13:22:20.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": null
  },
  {
    "id": 23,
    "title": "USSD Menu Manager",
    "url": "/menu-manager",
    "published_at": "2021-12-02T13:24:23.000Z",
    "created_at": "2021-12-02T13:24:20.000Z",
    "updated_at": "2021-12-02T13:24:23.000Z",
    "navigation": null,
    "parent": {
      "id": 21,
      "title": "USSD",
      "url": "/ussd",
      "published_at": "2021-12-02T13:22:20.000Z",
      "created_at": "2021-12-02T13:22:17.000Z",
      "updated_at": "2021-12-02T13:22:20.000Z",
      "navigation": null,
      "parent": null,
      "page": null
    },
    "page": null
  },
  {
    "id": 25,
    "title": "New WhiteList",
    "url": "/new-whitelist",
    "published_at": "2021-12-03T09:19:56.000Z",
    "created_at": "2021-12-03T09:19:52.000Z",
    "updated_at": "2021-12-03T09:19:56.000Z",
    "navigation": null,
    "parent": {
      "id": 16,
      "title": "Whitelist",
      "url": "/whitelist",
      "published_at": "2021-12-01T12:46:31.000Z",
      "created_at": "2021-12-01T12:46:25.000Z",
      "updated_at": "2021-12-01T12:46:31.000Z",
      "navigation": null,
      "parent": 15,
      "page": 10
    },
    "page": null
  }
]

```
```json
[
  {
    "id": 1,
    "title": "Intro",
    "parent": null,
    "children": []
  },
  {
    "id": 2,
    "title": "Messaging",
    "parent": null,
    "children": [
      {
        "id": 3,
        "title": "Message Category",
        "parent": [
          {
            "id": 2
          }
        ],
        "children": []
      },
      {
        "id": 4,
        "title": "Bulk Messaging",
        "parent": [
          {
            "id": 2
          }
        ],
        "children": [
          {
            "id": 5,
            "title": "Compose SMS with contact file",
            "parent": [
              {
                "id": 4
              }
            ],
            "children": []
          },
          {
            "id": 6,
            "title": "Send SMS from file",
            "parent": [
              {
                "id": 4
              }
            ],
            "children": []
          }
        ]
      },
      {
        "id": 7,
        "title": "DND",
        "parent": [
          {
            "id": 2
          }
        ],
        "children": [
          {
            "id": 8,
            "title": "Add Single member to DND",
            "parent": [
              {
                "id": 7
              }
            ],
            "children": []
          },
          {
            "id": 9,
            "title": "Bulk add to DND",
            "parent": [
              {
                "id": 7
              }
            ],
            "children": []
          }
        ]
      },
      {
        "id": 10,
        "title": "Logs",
        "parent": [
          {
            "id": 2
          }
        ],
        "children": []
      }
    ]
  },
  {
    "id": 11,
    "title": "Member Register",
    "parent": null,
    "children": [
      {
        "id": 12,
        "title": "Bulk Register",
        "parent": {
          "id": 11
        },
        "children": [
          {
            "id": 13,
            "title": "Whitelist",
            "parent": {
              "id": 12
            },
            "children": [
              {
                "id": 14,
                "title": "Blacklist",
                "parent": {
                  "id": 12
                },
                "children": []
              }
            ]
          }
        ]
      },
      {
        "id": 15,
        "title": "Single Register",
        "parent": {
          "id": 11
        },
        "children": [
          {
            "id": 16,
            "title": "Whitelist",
            "parent": {
              "id": 15
            },
            "children": [
              {
                "id": 25,
                "title": "New WhiteList",
                "parent": {
                  "id": 16
                },
                "children": []
              }
            ]
          },
          {
            "id": 17,
            "title": "Blacklist",
            "parent": {
              "id": 15
            },
            "children": []
          }
        ]
      }
    ]
  },
  {
    "id": 18,
    "title": "Support & changelog",
    "parent": null,
    "children": [
      {
        "id": 19,
        "title": "changelog",
        "parent": {
          "id": 18
        },
        "children": []
      },
      {
        "id": 20,
        "title": "Support",
        "parent": {
          "id": 18
        },
        "children": []
      }
    ]
  },
  {
    "id": 21,
    "title": "USSD",
    "parent": null,
    "children": [
      {
        "id": 22,
        "title": "USSD Logs",
        "parent": {
          "id": 21
        },
        "children": [
          {
            "id": 23,
            "title": "USSD Menu Manager",
            "parent": {
              "id": 21
            },
            "children": []
          }
        ]
      }
    ]
  }
]

```
```json
[
  {
    "id": 1,
    "title": "Intro",
    "children": []
  },
  {
    "id": 2,
    "title": "Messaging",
    "children": [
      {
        "id": 3,
        "title": "Message Category",
        "children": []
      },
      {
        "id": 4,
        "title": "Bulk Messaging",
        "children": [
          {
            "id": 5,
            "title": "Compose SMS with contact file",
            "children": []
          },
          {
            "id": 6,
            "title": "Send SMS from file",
            "children": []
          }
        ]
      },
      {
        "id": 7,
        "title": "DND",
        "children": [
          {
            "id": 8,
            "title": "Add Single member to DND",
            "children": []
          },
          {
            "id": 9,
            "title": "Bulk add to DND",
            "children": []
          }
        ]
      },
      {
        "id": 10,
        "title": "Logs",
        "children": []
      }
    ]
  },
  {
    "id": 11,
    "title": "Member Register",
    "children": [
      {
        "id": 12,
        "title": "Bulk Register",
        "children": [
          {
            "id": 13,
            "title": "Whitelist",
            "children": [
              {
                "id": 14,
                "title": "Blacklist",
                "children": []
              }
            ]
          }
        ]
      },
      {
        "id": 15,
        "title": "Single Register",
        "children": [
          {
            "id": 16,
            "title": "Whitelist",
            "children": [
              {
                "id": 25,
                "title": "New WhiteList",
                "children": []
              }
            ]
          },
          {
            "id": 17,
            "title": "Blacklist",
            "children": []
          }
        ]
      }
    ]
  },
  {
    "id": 18,
    "title": "Support & changelog",
    "children": [
      {
        "id": 19,
        "title": "changelog",
        "children": []
      },
      {
        "id": 20,
        "title": "Support",
        "children": []
      }
    ]
  },
  {
    "id": 21,
    "title": "USSD",
    "children": [
      {
        "id": 22,
        "title": "USSD Logs",
        "children": [
          {
            "id": 23,
            "title": "USSD Menu Manager",
            "children": []
          }
        ]
      }
    ]
  }
]

```
