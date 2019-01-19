# Comparator
package javaComparator.base;

import java.util.List;

public interface Comparator <T>{

	public void sirala(List<T> oyuncular);
	
	
}
package javaComparator.base;

import java.util.Arrays;
import java.util.List;

public class Oyuncu implements Comparator {

	String adı;
	int puan = 0;

	Oyuncu(int puan, String adı) {
		setAdı(adı);
		setPuan(puan);
	}

	public String getAdı() {
		return adı;
	}

	public void setAdı(String adı) {
		this.adı = adı;
	}

	public int getPuan() {
		return puan;
	}

	public void setPuan(int puan) {
		this.puan = puan;
	}

	@Override
	public void sirala(List temp) {
		// TODO Auto-generated method stub

		Object obj = null;
		for (int i = 0; i < temp.size(); i++) {
			for (int j = 0; j < temp.size(); j++) {
				if (((Oyuncu) (temp.get(i))).getPuan() > ((Oyuncu) (temp.get(j))).getPuan()) {
					obj = temp.get(i);
					temp.set(i, temp.get(j));
					temp.set(j, obj);
					j = j - 1;
				}
			}

		}

		for (Object tmp : temp) {
			System.out.println(((Oyuncu) tmp).getAdı() + " " + ((Oyuncu) tmp).getPuan());
		}
	}
}
package javaComparator.base;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class Runner {
//	static Scanner sc = new Scanner(System.in);
//	static String girilenad="";
//	static int girilenpuan=0;
	static List<Object> list = new ArrayList<Object>();
	
	
public static void main(String[] args) {
	Oyuncu o1 = new Oyuncu(10,"ali");
	Oyuncu o2 = new Oyuncu(6,"ahmet");
	Oyuncu o3 = new Oyuncu(50,"ayse");
	Oyuncu o4 = new Oyuncu(8,"hasan");
	Oyuncu o5 = new Oyuncu(10,"osman");
	Oyuncu o6 = new Oyuncu(50,"emel");
	list.add(o1);
	list.add(o2);
	list.add(o3);
	list.add(o4);
	list.add(o5);
	list.add(o6);
	
	o1.sirala(list);
	
	
	
	//while (girilenad!="") {}
	
}

//public void puangetir() {girilenpuan=sc.nextInt();}
//public void adgetir() {girilenad=sc.next();}
}
