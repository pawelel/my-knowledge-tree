---
{"title":"ToDo WPF Application","dg-publish":true,"tags":["coding/CSharp"],"language":"en","permalink":"/coding/c-sharp/to-do-wpf-application/","dgPassFrontmatter":true}
---

up:: [[coding/CSharp/CSharp\|CSharp]]

ToDo WPF Application is a simple application that uses the MVVM pattern and the WPF framework. My goal was to get a better understanding of the MVVM pattern and WPF in general. Below you can find some of my thoughts about the process.

## MVVM

Create base project and add class library with Core postfix. This will be the core of the application. Add a reference to the class library in the WPF project. The class library will contain the view models and the models. The WPF project will contain the views. In the .Core project add folders and classes:

* ViewModels
  * Pages
    * WorkTasksPageViewModel.cs
  * Controls
    * WorkTaskViewModel.cs
  * Base
  * BaseViewModel.cs
* Helpers
    RelayCommand.cs

In the main project add folders and classes:

* Pages
  * WorkTasksPage.xaml
  * WorkTasksPage.xaml.cs
* Controls
  * WorkTask.xaml
  * WorkTask.xaml.cs
* Styles
  * Buttons.xaml

## ViewModels

In the MainWindow.xaml add tag: `<local:WorkTasksPage/>`

In the WorkTasksPageViewModel.cs add the following code:

```csharp
namespace ToDoList.Core;
public class WorkTasksPageViewModel : BaseViewModel
{
    public ObservableCollection<WorkTasksViewModel> WorkTaskList { get; set; } = new();

    public string NewWorkTaskTitle { get; set; } = string.Empty;
    public string NewWorkTaskDescription { get; set; } = string.Empty;

    public ICommand AddNewWorkTaskCommand { get; set; }
    public ICommand DeleteSelectedTasksCommand { get; set; }

    public WorkTasksPageViewModel()
    {
        AddNewWorkTaskCommand = new RelayCommand(AddNewWorkTask);
        DeleteSelectedTasksCommand = new RelayCommand(DeleteSelectedTasks);
    }
    private void AddNewWorkTask()
    {
        WorkTaskList.Add(new WorkTasksViewModel
        {
            Title = NewWorkTaskTitle,
            Description = NewWorkTaskDescription,
            CreatedDate = DateTime.Now
        });
        NewWorkTaskTitle = string.Empty;
        NewWorkTaskDescription = string.Empty;

        OnPropertyChanged(nameof(NewWorkTaskTitle));
        OnPropertyChanged(nameof(NewWorkTaskDescription));
    }

    private void DeleteSelectedTasks()
    {
        // remove all selected observable objects

        if (WorkTaskList.Any(x => x.IsSelected))
        {
            List<WorkTasksViewModel> tasksList = WorkTaskList.ToList();
            tasksList.RemoveAll(x => x.IsSelected);
            WorkTaskList = new ObservableCollection<WorkTasksViewModel>(tasksList);
            OnPropertyChanged(nameof(WorkTaskList));
        }
    }
}
```

In the WorkTaskViewModel.cs add the following code:

```csharp
namespace ToDoList.Core;
public class WorkTasksViewModel
{
    public string Title { get; set; } = string.Empty;
    public string Description { get; set; } = string.Empty;
    public DateTime CreatedDate { get; set; }
}
```

In the BaseViewModel.cs add the following code:

```csharp
namespace ToDoList.Core;
public class BaseViewModel : INotifyPropertyChanged
{
    public event PropertyChangedEventHandler? PropertyChanged = (sender, eventArgs) => { };

    protected void OnPropertyChanged([CallerMemberName] string? propertyName = null)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }
}
```

In the RelayCommand.cs add the following code:

```csharp
namespace ToDoList.Core;
public class RelayCommand : ICommand
{
    private readonly Action _execute;
    
    public bool CanExecute(object? parameter)
    {
        return true;
    }

    public event EventHandler? CanExecuteChanged;

    public RelayCommand(Action execute)
    {
        _execute = execute;
    }
    public void Execute(object? parameter)
    {
        _execute();
    }
}
```

In the WorkTasksPage.xaml.cs add the following code:

```csharp
namespace ToDoList;
/// <summary>
/// Interaction logic for WorkTaskPage.xaml
/// </summary>
public partial class WorkTaskPage : Page
{
    public WorkTaskPage()
    {
        InitializeComponent();
        DataContext = new WorkTasksPageViewModel();
    }
}
```
