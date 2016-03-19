//sizeyunsuan 2
public class Main {
	
	public static void main(String[] args) {
		// TODO 自动生成的方法存根
		Scanner in=new Scanner(System.in);
		System.out.println("请输入数据范围 1- ");
		int  F=in.nextInt();
		
		
		System.out.println("请输入要生成的整数四则运算的个数 ");
		int n1=in.nextInt();
		
		System.out.println("有无乘除法   有输入1 没有输入0");
		 int Jiajian;
		 Jiajian=in.nextInt(); 
		 
		 System.out.println("加减无有负数  有输入1 没有输入0");
		 int Fu=in.nextInt();
		 
		 int Yv=3; 
		 if(Jiajian==1)
		 { 
			 System.out.println("除法有无余数 有输入1 没有输入0");
		       Yv=in.nextInt();
		 } 
		
	     
		 int Fis[]  =new int[n1];
	     int Sec[]  =new int[n1];
	     int Thr[]  =new int[n1];
         int i;
         
	    for(i =0;i<n1;i++)    
		  {
    	  Sec[i]=(int)(Math.random()*(F/2));
    	  Fis[i]=(int)(Math.random()*F);
         
		  if(Jiajian==0)
		  	{
		  Thr[i]=((int)(Math.random()*F))%2;
		  		}
		  if(Jiajian==1)
		  	{
			  Thr[i]=((int)(Math.random()*F))%4;
		  		}  
		  if(Thr[i]==3&&Sec[i]==0){Sec[i]++;}//防止除法里分母为0 ；
		  if(Yv==0&&Thr[i]==3){
        	  while(Fis[i]%Sec[i]!=0)
        	   { Fis[i]=Sec[i]*2;}   
           }
           if(Yv==1&&Thr[i]==3){
        	   while(Fis[i]%Sec[i]==0)
        	   { Fis[i]=(int)(Math.random()*F);}   
        	   
        	   if(Fu==0&&Thr[i]==1){
        		   while (Fis[i]<Sec[i]){ Fis[i]=(int)(Math.random()*F);}
        	   }
           }
		    
		  } 
	   
	   for(i=0;i<n1-1;i++)
	   {   
		   for(int j=i;j<n1-1;j++)
		   {
			   if((Fis[i]==Fis[j])&&(Sec[i]==Sec[j])&&(Thr[i]==Thr[j]))
			   {
				   Fis[i]=Fis[i]+1;
				   }
		   }
	   }//比较是否重复
	   
	 
	   for(i=0;i<n1;i++)    
		    {
		    if(Thr[i]==0)
	            System.out.println(Fis[i]+" + "+ Sec[i]+"=");
	 		if(Thr[i]==1)
	 			System.out.println(Fis[i]+" - "+ Sec[i]+"=");
	 		if(Thr[i]==2)
	 			System.out.println(Fis[i]+" * "+ Sec[i]+"=");
	 		if(Thr[i]==3)
	 			System.out.println(Fis[i]+" / "+ Sec[i]+"=");		
		    }
	  
	   
	   
	   
		 System.out.println("请输入要生成的分数四则运算的个数 ");
		 int n2=in.nextInt();  
	   int Fis1[]  =new int[n2];   
	   int Sec1[]  =new int[n2];  
	   int Thr1[]  =new int[n2];  
	   int Four[]  =new int[n2];  
	
	   
         for(int j=0;j<n2;j++)    
  	 	    {
	             Fis1[j]=(int)(Math.random()*F);
	             Sec1[j]=(int)(Math.random()*F);
  	             Thr1[j]=(int)(Math.random()*F);
	   		     Four[j]=(int)(Math.random()*F);
  		 
	   		     if( Fis1[j]> Sec1[j]){
	   		    	 	int Chang;
	   		    	 	Chang= Fis1[j]; Fis1[j]= Sec1[j]; Sec1[j]=Chang;
	   		     	}
  		
	   		     if(Thr1[j]>Four[j]){
	   		    	 	int Chang;
	   		    	 	Chang=Thr1[j];Thr1[j]=Four[j];Four[j]=Chang;
	   		     	}//交换大小
	   		     
    
  	   int Chang2=Fis1[j];
  		  for(int k=2;k<=Chang2;k++){
  			  if(Fis1[j]%k==0&& Sec1[j]%k==0)
  			  {
  				Fis1[j]=Fis1[j]/k;
  				Sec1[j]= Sec1[j]/k;
  				 k=1;
  			  }
  			  
  		  }
  		 int Chang3=Thr1[j];
  		for(int k=2;k<=Chang3;k++){
			  if(Thr1[j]%k==0&&Four[j]%k==0)
			  {
				  Thr1[j]=Thr1[j]/k;
				  Four[j]=Four[j]/k;
				  k=1;
			  }
		  }//化简真分数
  		
  		 
  		 while(Fis1[j]==0)
  		     { Fis1[j]=(int)(Math.random()*F);}
  		  while (Sec1[j]==0||Sec1[j]==Fis1[j]) 
  		     { Sec1[j]=(int)(Math.random()*F);} 
  		  while( Thr1[j]==0)
		     {  Thr1[j]=(int)(Math.random()*F);}
		  while (Four[j]==0||Four[j]== Thr1[j]) 
		     { Four[j]=(int)(Math.random()*F);} 
		  
		  	int x=(int)(Math.random()*F);
		
		  	for( i=0;i<n2-1;i++){
				   for(int k=i;k<n2-1;k++)
				   {
					   if(Fis1[i]==Fis1[j]&&Sec1[i]==Sec1[j]&&Thr1[i]==Thr1[j]&&Four[i]==Four[j])
					   {
						   Sec1[i]=Sec1[i]+1;
						   while (Sec1[i]==Fis1[i])
						   		{ Sec1[i]=Sec1[i]+1;}
					   }
				   }	
		  	}
  		if(x%4==0)
  			System.out.println(Fis1[j]+"/"+Sec1[j]+" + "+Thr1[j]+"/"+Four[j]+"=");
  		if(x%4==1)
  			System.out.println(Fis1[j]+"/"+Sec1[j]+" - "+Thr1[j]+"/"+Four[j]+"=");
  		if(x%4==2)
  			System.out.println(Fis1[j]+"/"+Sec1[j]+" * "+Thr1[j]+"/"+Four[j]+"=");
  		if(x%4==3)
  			System.out.println(Fis1[j]+"/"+Sec1[j]+" / "+Thr1[j]+"/"+Four[j]+"=");
  	     }
  	
											}
  
				}
