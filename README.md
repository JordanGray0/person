<p># person

<p>Form

<p>// declarations
<p>private ParkType parktype;
<p>private IKiosk _gen = new GenKioskWrap();
<p>private IKiosk _student = new StudentKioskWrap();
<p>private IKiosk _staff = new StaffKioskWrap();


<p>private void genRadBtn_CheckedChanged(object sender, EventArgs e){
       <p> {
     <p>       parktype = ParkType.General;
    <p>    }
<p>}


private btnCalculate {
	decimal number = convert.ToDecimal(groupBox.Text);
	if(parktype == ParkType.General){
		costLabel.Text = _gen.FindParkingAmount(hours).ToString("c");

	} else if {

	} else if {

	}
}
<p 
public class GenKioskWrap : IKiosk
	public decimal FindParkingAmount(decimal hours)
        {
            return _generalParkingKiosk.FindGeneralParkingAmount(hours);
        }	

public class GeneralParkingKiosk
    {
        public decimal FindGeneralParkingAmount(decimal hours)
        {
            return hours * 2;
        }
    }
		
public interface IKiosk
    {
        decimal HoursParked { get; }

        decimal FindParkingAmount(decimal hours);
    }
</p>
