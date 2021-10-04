import java.util.*;


public class TestAddressBook {

	public static void populateBook(){
		//AddressBook ab=new AddressBook();
		AddressBook.addNewAddress("Lakshmipuram", "Krishna", "Manikonda", "Hyderabad", "Telangana", "India", 500089);
		AddressBook.addNewAddress("Ch", "Prasanna", "Kanuru", "Vijayawada", "Andhra Pradesh", "India", 560034);
		AddressBook.addNewAddress("X", "Sowmya", "Kanuru", "Vijayawada", "Andhra Pradesh", "India", 560034);
	}

   public static void main(String []args) {
      populateBook();
	  
	  AddressBook.printMailingLabel();
	  
	  AddressBook.removeAddress("Krishna");
	  
	  AddressBook.printMailingLabel();
	  
	  AddressBook.addNewAddress("Lakshmipuram", "Krishna", "Manikonda", "Hyderabad", "Telangana", "India", 500089);
	  
	  AddressBook.printMailingLabel();
	  
	  AddressBook.addNewAddress("Lakshmipuram", "Krishna", "Manikonda", "Hyderabad", "Telangana", "India", 500089);
   }
}

class SingleAddress{
	private String lastName;
	private String firstName;
	private String streetAddress;
	private String city;
	private String state;
	private String country;
	private int postalCode;
	
	public String getLastName() {
		return lastName;
	}

	public void setLastName(String newLastName) {
		this.lastName = newLastName;
	}
	
	public String getFirstName() {
		return firstName;
	}

	public void setFirstName(String newFirstName) {
		this.firstName = newFirstName;
	}
	
	public String getStreetAddress() {
		return streetAddress;
	}

	public void setStreetAddress(String newStreetAddress) {
		this.streetAddress = newStreetAddress;
	}
	
	public String getCity() {
		return city;
	}

	public void setCity(String newCity) {
		this.city = newCity;
	}
	
	public String getState() {
		return state;
	}

	public void setState(String newState) {
		this.state = newState;
	}
	
	public String getCountry() {
		return country;
	}

	public void setCountry(String newCountry) {
		this.country = newCountry;
	}
	
	public int getPostalCode() {
		return postalCode;
	}

	public void setPostalCode(int newPostalCode) {
		this.postalCode = newPostalCode;
	}
	
	public String toString() { 
		return "FirstName: '" + this.firstName + "', LastName: '" + this.lastName + "', StreetAddress: '" + this.streetAddress + "', City: '" + this.city + "', State: '" + this.state;
	}
}


class AddressBook{
	static ArrayList<SingleAddress> addressList=new ArrayList<>();   
	
	public static void addNewAddress(String lastName, String firstName, String streetAddress, String city, String state, String country, int postalCode){
		try{
		
		SingleAddress sa=findByFirstName(firstName);
		if(sa!=null){
			//throw new DuplicateAddressException("Address already exists for the member");
			
			System.out.println("Address already exists for the member");
		}
		else{
			SingleAddress _singleAddress=new SingleAddress();
			_singleAddress.setLastName(lastName);
			_singleAddress.setFirstName(firstName);
			_singleAddress.setStreetAddress(streetAddress);
			_singleAddress.setCity(city);
			_singleAddress.setState(state);
			_singleAddress.setCountry(country);
			_singleAddress.setPostalCode(postalCode);
			
			addressList.add(_singleAddress);
		}
		}
		catch(Exception exc){
			throw exc;
		}
	}
	
	public static void removeAddress(String firstName){
		addressList.removeIf(obj -> obj.getFirstName() == firstName);
	}

	public static SingleAddress findByFirstName(String firstName) {
		return addressList.stream().filter(address -> firstName.equals(address.getFirstName())).findFirst().orElse(null);
	}
	
	public static void printMailingLabel(){
		for (int i = 0; i < addressList.size(); i++){
			System.out.println(addressList.get(i).toString());
		}
	}
}

class DuplicateAddressException extends Exception {  
    public DuplicateAddressException(String errorMessage) {  
    super(errorMessage);  
    }  
}  
