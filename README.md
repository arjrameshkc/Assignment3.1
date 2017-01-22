# Assignment3.1

Task1:

import java.io.*;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.fs.*;

public class Task1 {
	public static void main(String[] args) throws IOException {
        Configuration conf = new Configuration();
		Path path = new Path("hdfs://localhost:9000/");
        FileSystem fs = FileSystem.get(path.toUri(),conf);
        FileStatus[] fileStatus = fs.listStatus(path);
        for(FileStatus status : fileStatus){
            System.out.println(status.getPath().toString());
        }
  		}
}


Task2:


package Demo;
import java.io.*;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.fs.*;
import org.apache.hadoop.io.*;

public class Task2 {
	public static void main(String[] args) throws IOException {
      Configuration conf = new Configuration();
		Path path = new Path("hdfs://localhost:9000/");
      FileSystem fs = FileSystem.get(path.toUri(),conf);
      FileStatus[] fileStatus = fs.listStatus(path);
      for(FileStatus status : fileStatus){
    	  if (status.isDirectory()){
    		   System.out.println("Directory:"+ status.getPath().toString());
    	  }
    	  else
    	  {
    		  System.out.println("File:"+ status.getPath().toString());
    	  }
      }
		}
}

Task3:

package Demo;
import java.io.*;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.fs.*;

public class Task3 {
	public static void main(String[] args) throws IOException {
      Configuration conf = new Configuration();
		Path path1 = new Path("hdfs://localhost:9000/");
      FileSystem fs = FileSystem.get(path1.toUri(),conf);
      FileStatus[] fileStatus = fs.listStatus(path1);
      for(FileStatus status : fileStatus){
    	  if (status.isDirectory()){
    		   System.out.println("Directory:"+ status.getPath().toString());
    	  }
    	  else
    	  {
    		  System.out.println("File:"+ status.getPath().toString());
    	  }
      }
      Configuration conf1 = new Configuration();
		Path path2 = new Path("hdfs://localhost:9000/ramesh");
    FileSystem fs1 = FileSystem.get(path2.toUri(),conf1);
    FileStatus[] fileStatus1 = fs1.listStatus(path2);
    for(FileStatus status1 : fileStatus1){
  	  if (status1.isDirectory()){
  		   System.out.println("Directory:"+ status1.getPath().toString());
  	  }
  	  else
  	  {
  		  System.out.println("File:"+ status1.getPath().toString());
  	  }
    }
		}
}
