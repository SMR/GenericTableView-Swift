# GenericTableView-Swift
Creates a easily reusable TableViewController.

##Supported Platforms

- iOS 9
- swift 2.2

##Installing

In order to install, you'll need to copy the `GenericTableViewController` file into your Xcode project. 

##Usage

###Using the ConfigureTable struct constructor:

* items - this is the collection you want to show in the tableview
* cellType - This is the UITableViewCell class you want to use
* configureCell - This is a closure with your cell configuration
* selectedRow - This is a closure that will be fired when a cell is touched

```swift
  ConfigureTable(items: [Item], 
              cellType: AnyClass, 
              configureCell:(cell: UITableViewCell, item: Item) -> (), 
              selectedRow:(tableView: UITableView, indexPath: NSIndexPath) -> ())
```

###Sample:
```swift
let names = ["John", "Clark", "Peter", "Tim", "Zack", "Adam"].sort()
let config = ConfigureTable(items: names, 
                          cellType: UITableViewCell.self, 
                          configureCell: { (cell, item) in
                                        cell.textLabel?.text = "\(item)"
                          }) { (tableView, indexPath) in
                                        let cell = tableView.cellForRowAtIndexPath(indexPath)
                                        print(cell?.textLabel?.text)
                         }
        
let main = GenericTableViewController(config: config)
```

##License

`GenericTableViewController` is licensed under the MIT license.
