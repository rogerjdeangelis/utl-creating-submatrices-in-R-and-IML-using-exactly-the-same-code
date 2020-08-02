# utl-creating-submatrices-in-R-and-IML-using-exactly-the-same-code
Creating submatrices in R and IML using exactly the same code
  Creating submatrices in R and IML using exactly the same code                                                        
                                                                                                                       
  I think it behooves every SAS programer to experiment with R and Python.                                             
                                                                                                                       
  github                                                                                                               
  https://tinyurl.com/y6zho7go                                                                                         
  https://github.com/rogerjdeangelis/utl-creating-submatrices-in-R-and-IML-using-exactly-the-same-code                 
                                                                                                                       
  SAS Forum                                                                                                            
  https://tinyurl.com/y5x26vjh                                                                                         
  https://communities.sas.com/t5/SAS-IML-Software-and-Matrix/how-to-index-submatrices/m-p/673884                       
                                                                                                                       
  R snd Python both support SQL and mstrix like languages that aare very close to SAS 'SQ'L and 'proc IML'.            
                                                                                                                       
  Problem: Create four 3x3 submatrices from a 6x6 matrix using the same code in R and SAS                              
                                                                                                                       
         Two Solutions                                                                                                 
                                                                                                                       
              a. SAS                                                                                                   
                 Rick                                                                                                  
                 https://communities.sas.com/t5/user/viewprofilepage/user-id/13684                                     
              b. R                                                                                                     
                                                                                                                       
  /*                   _                                                                                               
  (_)_ __  _ __  _   _| |_                                                                                             
  | | `_ \| `_ \| | | | __|                                                                                            
  | | | | | |_) | |_| | |_                                                                                             
  |_|_| |_| .__/ \__,_|\__|                                                                                            
          |_|                                                                                                          
  */                                                                                                                   
                                                                                                                       
  * This code works as is in SAS and R. Note I convert the submatrices to R dataframes                                 
  because I wante to output SAS datasets. Remove 'as.data.frame' if you                                                
  want to work with R matrices.                                                                                        
                                                                                                                       
  * Identical code ;                                                                                                   
                                                                                                                       
  A = toeplitz(6:1);                                                                                                   
  /*   A[rows, cols] */                                                                                                
  A1 = A[1:3, 1:3];                                                                                                    
  A2 = A[1:3, 4:6];                                                                                                    
  A3 = A[4:6, 1:3];                                                                                                    
  A4 = A[4:6, 4:6];                                                                                                    
  );                                                                                                                   
                                                                                                                       
   WORK.A                                                                                                              
                                                                                                                       
  ------------------------------------------------------------------                                                   
  |       V1         V2         V3         V4         V5         V6|                                                   
  |----------------------------------------------------------------|                                                   
  |        6|         5|         4|         3|         2|         1|                                                   
  |---------+----------+----------+----------+----------+----------|                                                   
  |        5|         6|         5|         4|         3|         2|                                                   
  |---------+----------+----------+----------+----------+----------|                                                   
  |        4|         5|         6|         5|         4|         3|                                                   
  |---------+----------+----------+----------+----------+----------|                                                   
  |        3|         4|         5|         6|         5|         4|                                                   
  |---------+----------+----------+----------+----------+----------|                                                   
  |        2|         3|         4|         5|         6|         5|                                                   
  |---------+----------+----------+----------+----------+----------|                                                   
  |        1|         2|         3|         4|         5|         6|                                                   
  ------------------------------------------------------------------                                                   
                                                                                                                       
  /*           _               _                                                                                       
    ___  _   _| |_ _ __  _   _| |_                                                                                     
   / _ \| | | | __| `_ \| | | | __|                                                                                    
  | (_) | |_| | |_| |_) | |_| | |_                                                                                     
   \___/ \__,_|\__| .__/ \__,_|\__|                                                                                    
                  |_|                                                                                                  
  */                                                                                                                   
                                                                                                                       
  SAS DATASETS                                                                                                         
                                                                                                                       
      A1           A2                                                                                                  
                                                                                                                       
  ----------   -----------                                                                                             
  |V1 V2 V3|   |V1 V2 V3|                                                                                              
  |---------   ---------|                                                                                              
  | 6  5  4|   | 3  2  1|                                                                                              
  |--------+   +--------|                                                                                              
  | 5  6  5|   | 4  3  2|                                                                                              
  |--------+   +--------|                                                                                              
  | 4  5  6|   | 5  4  3|                                                                                              
  |--------+   +--------|                                                                                              
                                                                                                                       
      A3           A4                                                                                                  
                                                                                                                       
  ----------   ----------                                                                                              
  |V1 V2 V3|   |V1 V2 V3|                                                                                              
  |--------+   +--------|                                                                                              
  | 3  4  5|   | 6  5  4|                                                                                              
  |--------+   +--------|                                                                                              
  | 2  3  4|   | 5  6  5|                                                                                              
  |--------+   +--------|                                                                                              
  | 1  2  3|   | 4  5  6|                                                                                              
  ----------   -----------                                                                                             
                                                                                                                       
  /*         _       _   _                                                                                             
   ___  ___ | |_   _| |_(_) ___  _ __                                                                                  
  / __|/ _ \| | | | | __| |/ _ \| `_ \                                                                                 
  \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                
  |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                
    __ _     ___  __ _ ___                                                                                             
   / _` |   / __|/ _` / __|                                                                                            
  | (_| |_  \__ \ (_| \__ \                                                                                            
   \__,_(_) |___/\__,_|___/                                                                                            
  */                                                                                                                   
  proc datasets lib=work;                                                                                              
    delete A:;                                                                                                         
  run;quit;                                                                                                            
                                                                                                                       
  proc iml;                                                                                                            
                                                                                                                       
  * same in R;                                                                                                         
                                                                                                                       
  A = toeplitz(6:1);                                                                                                   
  /*   A[rows, cols] */                                                                                                
  A1 = A[1:3, 1:3];                                                                                                    
  A2 = A[1:3, 4:6];                                                                                                    
  A3 = A[4:6, 1:3];                                                                                                    
  A4 = A[4:6, 4:6];                                                                                                    
                                                                                                                       
                                                                                                                       
  create A1 from A1; append from A1;close A1;                                                                          
  create A2 from A2; append from A2;close A2;                                                                          
  create A3 from A3; append from A3;close A3;                                                                          
  create A4 from A4; append from A4;close A4;                                                                          
  ;quit;                                                                                                               
                                                                                                                       
  LOG                                                                                                                  
                                                                                                                       
  NOTE: IML Ready                                                                                                      
  443    &code                                                                                                         
  444   create A1 from A1; append from A1;close A1;                                                                    
  NOTE: The data set WORK.A1 has 3 observations and 3 variables.                                                       
  445   create A2 from A1;                                                                                             
  445 !                    append from A2;                                                                             
  445 !                                   close A2;                                                                    
  NOTE: The data set WORK.A2 has 3 observations and 3 variables.                                                       
  446   create A3 from A1;                                                                                             
  446 !                    append from A3;                                                                             
  446 !                                   close A3;                                                                    
  NOTE: The data set WORK.A3 has 3 observations and 3 variables.                                                       
  447   create A4 from A1;                                                                                             
  447 !                    append from A4;                                                                             
  447 !                                   close A4;                                                                    
  NOTE: The data set WORK.A4 has 3 observations and 3 variables.                                                       
  448   ;quit;                                                                                                         
  NOTE: Exiting IML.                                                                                                   
                                                                                                                       
  /*        ____                                                                                                       
  | |__    |  _ \                                                                                                      
  | `_ \   | |_) |                                                                                                     
  | |_) |  |  _ <                                                                                                      
  |_.__(_) |_| \_\                                                                                                     
                                                                                                                       
  */                                                                                                                   
                                                                                                                       
  %utlfkil(d:/xpt/want.xpt);                                                                                           
  proc datasets lib=work;                                                                                              
    delete A:;                                                                                                         
  run;quit;                                                                                                            
                                                                                                                       
  %utl_submit_r64(resolve('                                                                                            
  library(SASxport);                                                                                                   
  /* same as SAS with slight change to use dataframes */                                                               
  A  = as.data.frame(toeplitz(6:1));                                                                                   
  A1 = A[1:3, 1:3];                                                                                                    
  A2 = A[1:3, 4:6];                                                                                                    
  A3 = A[4:6, 1:3];                                                                                                    
  A4 = A[4:6, 4:6];                                                                                                    
  A1;A2;A3;A4;                                                                                                         
  write.xport(A, A1, A2, A3, A4,file="d:/xpt/want.xpt");                                                               
  '));                                                                                                                 
                                                                                                                       
  libname xpt xport "d:/xpt/want.xpt";                                                                                 
  proc copy in=xpt out=work;                                                                                           
  run;quit;                                                                                                            
  libname xpt clear;                                                                                                   
                                                                                                                       
  LOG                                                                                                                  
                                                                                                                       
  NOTE: Input library XPT is sequential.                                                                               
  NOTE: Copying XPT.A to WORK.A (memtype=DATA).                                                                        
  NOTE: There were 6 observations read from the data set XPT.A.                                                        
  NOTE: The data set WORK.A has 6 observations and 6 variables.                                                        
  NOTE: Copying XPT.A1 to WORK.A1 (memtype=DATA).                                                                      
  NOTE: There were 3 observations read from the data set XPT.A1.                                                       
  NOTE: The data set WORK.A1 has 3 observations and 3 variables.                                                       
  NOTE: Copying XPT.A2 to WORK.A2 (memtype=DATA).                                                                      
  NOTE: There were 3 observations read from the data set XPT.A2.                                                       
  NOTE: The data set WORK.A2 has 3 observations and 3 variables.                                                       
  NOTE: Copying XPT.A3 to WORK.A3 (memtype=DATA).                                                                      
  NOTE: There were 3 observations read from the data set XPT.A3.                                                       
  NOTE: The data set WORK.A3 has 3 observations and 3 variables.                                                       
  NOTE: Copying XPT.A4 to WORK.A4 (memtype=DATA).                                                                      
  NOTE: There were 3 observations read from the data set XPT.A4.                                                       
  NOTE: The data set WORK.A4 has 3 observations and 3 variables.                                                       
  NOTE: PROCEDURE COPY used (Total process time):                                                                      
                                                                                                                       
                                                                                                                       
