# .NET e C#
## C#
- linguaggio object oriented
- Tipizzazione forte e statica
- Garbage Collection
- Type Safety
- Compilato e Interpretato
- Codice viene compilato in CIL (Common Intermediate Language) (stessa idea del bytecode) per essere poi trasformato in linguaggio macchina
- Supporta struct
  ```c#
    struct Punto {
        public int X;
        public int Y;
    }
  ```
  ### Sintassi

  - String interpolation
    ```c#
    Console.WriteLine($"{nome} ha {età} anni e è alto {altezza}m.");
    ```
  - Array
    ```c#
      string[] frutti = { "mela", "banana", "arancia", "kiwi" };
    ```
  - Foreach
    ```c#
      foreach (string frutto in frutti) {
          Console.WriteLine(frutto);
      }
    ```
  - Metodi Liste
    ```c#
    List<string> frutti = new List<string>();
    frutti.Add("Mela");
    frutti.Add("Banana");
    frutti.Insert(1, "Arancia");
    Console.WriteLine($"Numero di frutti: {frutti.Count}");
    frutti[0] = "Mela verde";
    frutti.Remove("Banana");
    frutti.Sort();
    string[] arrayFrutti = frutti.ToArray();
  
    ```
  - Oggetti
 
    ```c#
    class Persona {
        public string Nome { get; set; }
        public int Età { get; set; } //funzionano come getter e setter
    
        public void Presentati(){
          Console.WriteLine($"Ciao, sono {Nome} e ho {Età} anni.");
        }
    }
    ```
  - LINQ (Language integrated Query) sintassi simile per estrarre dagli array, oggetti, ecc
 
    ```c#
     int SomeValue = 5; 
     var results =  from c in SomeCollection
                    let x = SomeValue * 2
                    where c.SomeProperty < x
                    select new {c.SomeProperty, c.OtherProperty};
     foreach (var result in results)
             Console.WriteLine(result);
    ```

## WinUI

- Model: dati e logica di business (simile a MVC)
  ```c#
    public class UserModel {
        public string Name { get; set; }
        public string Email { get; set; }
    }

  ```
- View: presentazione dei dati (XAML)

  ```xaml
    <StackPanel>
        <TextBox Text="{Binding Name, Mode=TwoWay}"/>
        <TextBox Text="{Binding Email, Mode=TwoWay}"/>
    </StackPanel>

  ```
- ViewModel: mediatore tra Model e View, gestisce la logica di presentazione

  ```c#
  public class UserViewModel : INotifyPropertyChanged { 
      private UserModel _user;
      public string Name { 
        get => _user.Name;
        set { _user.Name = value;
              OnPropertyChanged(); }
      }
      public event PropertyChangedEventHandler PropertyChanged; // dichiara un evento pubblico (standard)
      protected virtual void OnPropertyChanged([CallerMemberName] string propertyName = null) { 
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
      }
  }

  ```
- Separazione netta tra UI e logica, facilità di test, idoneità per XAML
- [Model] <--> [ViewModel] <---(Data Binding)---> [View]

- Data Binding puo' essere OneWay (utile per visualizzare dati) o TwoWay (utile per forme input)
  ```xaml
    <TextBox Text="{Binding Name, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}"/> 
    <TextBlock Text="{Binding Email, Converter={StaticResource EmailValidator}}"/>
    <Button Content="Salva" Command="{Binding SaveCommand}"/>
  ```
- Utilizzato XAML (extensible  application markup language) un linguaggio dichiarativo basato su xml

  ### Esempi di XAML
- `TextBlock`: per testo non modificabile
- `TextBox`: per input di testo
- `Button`: per azioni dell'utente
- `CheckBox`: per selezioni booleane
- `RadioButton`: per selezioni mutuamente esclusive
- `StackPanel`: impila elementi verticalmente o orizzontalmente
- `Grid`: layout a griglia flessibile
- `Canvas`: posizionamento assoluto
- `WrapPanel`: dispone elementi in righe o colonne
- `ProgressBar`: per mostrare avanzamento
- `Image`:
  ```xaml
    <Image Source="ms-appx:///Assets/logo.png" Width="100" Height="100" />
  ```
- `NavigationView`: per creare layout di applicazioni moderne con navigazione strutturata
```xaml
  <NavigationView PaneTitle="App Navigation">
    <NavigationView.MenuItems>
        <NavigationViewItem Content="Home" Icon="Home" />
        <NavigationViewItem Content="Impostazioni" Icon="Settings" />
    </NavigationView.MenuItems>
</NavigationView>
```
- 



### Multi Pagina
- Page rappresentano le singole schermate
- Frame e' il contenitore di navigazione
- Logica di navigazione necessaria


```xaml
<Frame x:Name="MainFrame"/>
```
```c#
public sealed partial class MainWindow : Window {
    public MainWindow() {
        this.InitializeComponent();
        MainFrame.Navigate(typeof(HomePage));
    }
}
```

- Navigazione

```c#
  MainFrame.Navigate(typeof(DetailsPage), someData);
  if (MainFrame.CanGoBack) {
      MainFrame.GoBack();
  }

```

### Conservazione dati
- file locali
- StorageFolder
  ```c#
  StorageFolder storageFolder = KnownFolders.DocumentsLibrary;
  StorageFile sampleFile = await storageFolder.CreateFileAsync("sample.txt", CreationCollisionOption.ReplaceExisting);
  await FileIO.WriteTextAsync(sampleFile, "Contenuto del file");
  ```
- SQLite
- Spazi di archiviazione offerti dalla piattaforma Windows:
  -  LocalFolder: spazio locale persistente per dati specifici
  -  RoamingFolder: sincronizzare impostazioni tra diversi dispositivi
  -  TemporaryFolder: spazio temporaneo



### Network

- HttpClient
  ```c#
  static readonly HttpClient client = new HttpClient();
  HttpResponseMessage response = await client.GetAsync("https://api.example.com/data");
      if (response.IsSuccessStatusCode) {
          string responseData = await response.Content.ReadAsStringAsync();
          // Gestione dei dati ricevuti
      }

  ```
- Possibile serializzare e deserializzare su un oggetto
  ```c#
  var persona = new Persona { Nome = "Luca", Età = 25 };
  string jsonString = JsonSerializer.Serialize(persona);
  string jsonString = "{\"Nome\":\"Luca\",\"Età\":25}";
  Persona persona = JsonSerializer.Deserialize<Persona>(jsonString);

  ```


### Distribuzione
- Msix: formatto MSI e APPX, app isolate tra loro, aggiornamenti incrementali
- Microsoft Store
- Necessario un manifest per indicare i permessi, nomi, ecc












    
