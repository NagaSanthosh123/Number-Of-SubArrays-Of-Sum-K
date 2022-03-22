# Number-Of-SubArrays-Of-Sum-K
import java.util.*;
public class NumberOfSubArraysOfSumK {

	public static void main(String[] args) {
		
		HashMap<Integer,Integer> m=new HashMap<>();
		int arr[]= {3,4,7,2,-3,1,4,2};
		m.put(0, -1);
		int s=0;
		int k=7;
		int max=0,c=0,ind1=0,ind2=0;
		for(int i=0;i<arr.length;i++) {
			s+=arr[i];
			if(m.containsKey(s-k)) {
				int ind=m.get(s-k);
				c+=1;
				max=Math.max(max, i-ind);
				if(i-ind==max) {
					ind1=ind;
					ind2=i;
				}
			}
			if(!m.containsKey(s)) {
				m.put(s, i);
			}
		}
		System.out.println(max);
		System.out.println(c);
		System.out.println(ind1+1+" "+ind2);
		
		
		
	}

} 
