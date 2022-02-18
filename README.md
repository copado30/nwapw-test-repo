# nwapw-test-repo
#include <iostream>
#include <fstream>
#include <iomanip>

 using namespace  std;

  int main() {
    ifstream inFile;
    string Open_File, CityName, Sname;
    char text [1024];
    double Gprice, OAvg, WAvg, CAvg, Osum, Wsum, Csum, sum, TotOr, TotWa,TotCa,Total, GpOr, GpCa, GpWa, Tsum,TAvg;
  


    cout<< " Enter the name of the file"<<endl;
    cout<< " File name should be 'gasprices.txt' "<<endl;
    cin >> text;
    inFile.open( text);

    inFile>> CityName>> Sname>> Gprice;
    cout << CityName << " " << Sname << "  "<< Gprice << endl;
    sum=0 , Wsum=0, Osum=0,Csum=0, TotOr=0, TotCa=0, TotWa=0, Total=0;

      while (inFile) {
      sum = sum + Gprice;
      inFile >> CityName >>Sname >> Gprice;
    cout << CityName << " " << Sname << "  "<< Gprice << endl;
      if (Sname == "Or"){
      TotOr= TotOr + 1; 
      Osum= Osum+ Gprice;

      }
      if (Sname == "Ca"){
      TotCa= TotCa + 1; 
      Csum = Csum + Gprice;

      }

      if (Sname == "Wa"){
      TotWa = TotWa + 1;
      Wsum= Wsum + Gprice;
    }
      if(Sname == "Wa" or Sname == "Ca" or Sname == "Or"){
        Total= Total + 1;
      Tsum = Tsum + Gprice;

      }
    
    }
    OAvg = Osum/TotOr;
    WAvg= Wsum/TotWa;
    CAvg= Csum/TotCa;
    TAvg= Tsum/Total;
    cout<< "The average price of gas in Oregon is: "<< OAvg<< endl;
    cout<< "The average price of gas in Washington is: "<<WAvg<< endl;
    cout<< "The average price of gas in California is: "<< CAvg << endl;
    cout << "The grand average is: "<< TAvg <<endl;

    if (OAvg < CAvg && OAvg < WAvg){
    cout<< "Oregon has the cheapest gas prices"<< endl;

    }
    if ( WAvg < CAvg && WAvg < OAvg ){
  cout << "Washington has the cheapest gas prices" << endl;
    }
    if ( CAvg < WAvg && CAvg < OAvg) {
      cout << "California has the cheapest gas prices" << endl; 
    }
    if (OAvg > CAvg && OAvg > WAvg){
    cout<< "Oregon has the most expensive gas prices"<< endl;

    }
    if ( WAvg > CAvg && WAvg > OAvg ){
  cout << "Washington has the most expensive gas prices" << endl;
    }
    if (  CAvg> WAvg && CAvg > OAvg) {
      cout << "California has the most expensive gas prices" << endl; 
    }
  } 
