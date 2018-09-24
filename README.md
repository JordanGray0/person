iDisplay - Display.	
iSubject	NotifyObservers	RegisterObservers(o)	RemoveObservers(o).
iObserver - Update.	

concrete subject _observers _output Output , ConcreteSubject NotifyObservers RegisterObservers, RemoveObservers.
ConcreteObserver1 ConcreteObserver1 Display Update.

public partial class ConcreteSubject : Form, iSubject.
private List<iObserver> _observers = new List<iObserver>();.
public ConcreteSubject()
        {
            InitializeComponent();
            ConcreteObserver1 CO1 = new ConcreteObserver1(this);
            CO1.Show();
        }	
	public int Output
        {
            get
            {
                return _output;
            }
            set
            {
                _output = value;
            }
        }
	
	 int.TryParse(textBox1.Text, out _propertyX);

public partial class ConcreteObserver1 : Form, iObserver, iDisplay
private iSubject _subject;
private int _output;
public ConcreteObserver1(iSubject s)
        {
            InitializeComponent();
            _subject = s;
        }
	
public void Display()
        {
            ConcreteOutputLabel1.Text = _output.ToString();
        }	
	
public void Update(int x)
        {
            _output = x;
            outputlabelconcrete.text = _output.ToString();
        }	
	
program.cs
Application.Run(new ConcreteSubject());
	
