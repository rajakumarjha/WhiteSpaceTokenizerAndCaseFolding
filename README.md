# WhiteSpaceTokenizerAndCaseFolding
##White Space tokenization:
Simply through white   space. Hyphen, apostrophes are not considered at all.
Issue with white space tokenization: “I’m” is one single word but it actually mean “I am”. Similarly a name of a person like “Raja Kumar” should be treated as one word but white space tokenization will count it as two. There are lot many problems with identification of symbols too in white space tokenization. 

##Case Folding
Case folding: Entire input either in small letter or capital letter. In general into small letter word so that two words like RAJA and Raja will be treated same.
Issue with case folding: Meaning of an acronym is lost example “US” is converting into “us”. Clever indexing algorithms can overcome even this problem example algorithm based on user profile, location, user history etc.
 code:
 
< public class WhiteSpaceTokenizer {
	public static void main(String []args){
		Scanner sc=new Scanner(System.in);
		System.out.println("Enter the string to be tokenised: ");
		
		String str=sc.nextLine();
		
		String []tokens=str.split(" ");
		System.out.println("Total size is: "+ tokens.length);
		for(int i=0;i<tokens.length;i++){
			//Case folding....
			String s= tokens[i];
			tokens[i]= s.toLowerCase();
		}
		System.out.println(tokens[0]);
	}

}>
