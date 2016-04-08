package kk;

import java.io.BufferedReader;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.util.*;

class Studentsss implements Comparator< Studentsss >, Comparable< Studentsss >{
	private String name;
	private String r;
	private int l1;
	private int l2;
	private int m;
	private int s;
	private int es;
	private int total;
	Studentsss(){
	}
	Studentsss(String n, String roll, int lang1, int lang2, int math, int sci, int enst){
		name=n;
		r=roll;
		l1=lang1;
		l2=lang2;
		m=math;
		s=sci;
		es=enst;
		total = (l1+l2+m+s+es);
	}
	public String getStudentsssName(){
		return name;
	}
	//public int getStudentssstot(){
	//	return total;
	//}
	// Overriding the compareTo method
	public int compareTo(Studentsss d){
		return (this.name).compareTo(d.name);
	}
	// Overriding the compare method to sort the age 
	public int compare(Studentsss d, Studentsss d1){
		if(d.total != d1.total) return d1.total - d.total;
		if(d.m != d1.m) return d1.m- d.m;
		if(d.s != d1.s) return d1.s-d.s;
		if(d.es != d1.es) return d1.es-d.es;
		if(d.l1 != d1.l1) return d1.l1-d.l1;
		return d1.l2-d.l2;
		
	}
}
public class ranking_systems{
	public static void main(String args[]){
		// Takes a list o Studentsss objects
		int i=1;
		List< Studentsss> list = new ArrayList<Studentsss>();
		//List<String> list = FileUtils.readLines(new File("/path/to/file.txt"), "utf-8");
		Scanner b= new Scanner(System.in);
        int n =b.nextInt();
        //String name[] =new String[n];
        for(int j=0;j<n;j++)
        {
            String name =b.next();
            String no=b.next();
            int l1= b.nextInt();
            int l2= b.nextInt();
            int m= b.nextInt();
            int s= b.nextInt();
            int es= b.nextInt();
            //int h= s.nextInt();
            
            list.add(new Studentsss(name,no,l1,l2,m,s,es));
        }
        
		//list.add(new Studentsss("A","R1",90,80,88,78,58));
		//list.add(new Studentsss("B","R2",60,80,88,77,89));
		//list.add(new Studentsss("C","R3",80,58,88,78,90));
		//list.add(new Studentsss("D","R4",100,90,98,97,98));
		//list.add(new Studentsss("E","R5",100,90,98,97,99));
		Collections.sort(list);// Sorts the array list
		for(Studentsss a: list)//printing the sorted list of names
		System.out.print(a.getStudentsssName() + ", ");
		// Sorts the array list using comparator
		Collections.sort(list, new Studentsss());
		System.out.println(" ");
		for(Studentsss a: list){//printing the sorted list of ages
			System.out.println(a.getStudentsssName() +" : "+ i );
			i++;
		}
	
	}
}