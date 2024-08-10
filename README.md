# Power Automate SharePoint List Hide/Show

This project provides a solution for hiding or showing items in SharePoint lists based on specific conditions using Microsoft Power Automate. This solution allows you to dynamically manage the visibility of list items, enhancing user experience and data organization within SharePoint.

## How It Works

1. Variable Creation: A variable named "true_or_false" is created. This variable contains the command to hide or show items in the list.
2. Site Link Creation: A "Compose" action is added and named "Site Link". This action includes the name of the SharePoint site.
3. List Name Creation: Another "Compose" action is added and named "List Name". This action contains the name of the list you want to hide or show.
4. Sending HTTP Request to SharePoint: A "Send an HTTP request to SharePoint" action is added, with the following commands configured:
- Site Address: Site Link
- Method: POST
- Uri: _api/web/lists/getbytitle('your_List_Name')
- Headers:
    - X-HTTP-Method: MERGE
    - If-Match: *
- Body:
```json
{
  "Hidden": @{variables('true_or_false')}
}
```
![1](https://github.com/korhanh/Power_Automate_SharePoint_List_Hide_Show/blob/main/1.png)

![2](https://github.com/korhanh/Power_Automate_SharePoint_List_Hide_Show/blob/main/2.png)

## Features

- Dynamic Visibility Management: Hide or show items in SharePoint lists based on conditions.
- Flexible and Easy to Use: Easily configure SharePoint site and list names.
- Efficient Workflow Management: Optimize data organization by managing the visibility of list items.
- Seamless Integration: Easily integrated with SharePoint and adaptable to existing workflows.

## Requirements

- Microsoft Power Automate subscription
- Basic understanding of SharePoint
- Basic knowledge of Power Automate flow creation

## Getting Started

- Add the steps outlined above to your Power Automate flow.
- Adjust the site and list names according to your needs.
- Use the variable ("true_or_false") to hide or show items.

## Contributions and Feedback

Contributions to this project are welcome! If you encounter any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](https://github.com/korhanh/Power_Automate_SharePoint_List_Hide_Show/blob/main/LICENSE).

Feel free to use, modify, and distribute this project according to the terms specified in the license.

## Credits

This project is created and maintained by [korhanh]([link_to_your_github_profile](https://github.com/korhanh)).

If you use this project or find it helpful, consider giving it a star on GitHub!

Happy Hide or Show SP List! :rocket:
