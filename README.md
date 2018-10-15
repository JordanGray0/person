 public class Theatre
    {
private Seat[,] _seats;

public Theatre(string myName, string myAddress)
        {
		//field, property
            _theatreName = myName;
            _theatreAddress = myAddress;
            InitializeSeats();
        }
	
	
	public void InitializeSeats()
        {
            _seats = new Seat[,] {
	    _totalSeatsinTheatre = 60;
            _completelyVacant = true;
        }

  public string PleaseBookSeats(int NumberOfSeats)
        {
            if (NumberOfSeats > 60)
            {
                return "only 60 seats";
            }
            else if (_currentVacantSeats == 0)
            {
                return "Sorry, there is no seat left";
            }
            else if (NumberOfSeats > _currentVacantSeats)
            {
                return "Sorry, there are not enough seats";
            }
            else
            {
                _currentVacantSeats -= NumberOfSeats;
                _lastBookedSeatDetails = "";
                foreach (Seat s in _seats)
                {
                    if (NumberOfSeats == 0)
                    {
                        break;
                    }
                    else
                    {
                        if (s.IsVacant == true)
                        {
                            _lastBookedSeatDetails += s.RowNumber.ToString() + s.SeatNumber.ToString() + " booked" + Environment.NewLine;
                            NumberOfSeats -= 1;
                            s.IsVacant = false;
                        }
                    }
                }
                _completelyVacant = false;
                return _lastBookedSeatDetails;
            }

            }
 public void ResetAllSeatsForNewShow()
        {
            InitializeSeats();
        }
	//seats
	public Seat(char myRowNumber, int mySeatNumber)
        {
            _rowNumber = myRowNumber;
            _seatNumber = mySeatNumber;
            _isVacant = true;
        }
	
	 public bool IsVacant
        {
            get
            {
                return _isVacant;
            }

            set
            {
                _isVacant = value;
            }
        }

unitTesting
 Theatre theatre;
  theatre = new Theatre("Massey", "NorthShore");
  
    [TestMethod]
    public void TestInitialEmptySeats()
        {
            int expected = 60;
            int actual = theatre.CurrentVacantSeats;
            Assert.AreEqual(expected, actual);
        }
	
	  [TestMethod]
        public void TestResetAllSeatsForNewShow()
        {
            theatre.ResetAllSeatsForNewShow();
            int expected = 60;
            int actual = theatre.CurrentVacantSeats;
            Assert.AreEqual(expected, actual);
        }
