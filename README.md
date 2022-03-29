using System;
using System.Collections.Generic;
using System.Text;
using System.Data.SqlClient;

namespace EmployeeManagementSystem
{
    class UpdateEmployeeDetails
    {
        public SqlConnection connection = null;
        public UpdateEmployeeDetails()
        {
            EmployeeProject employeeProject = new EmployeeProject();

          
            Console.WriteLine(" 1.Update EmployeeName\n " +
                            "2.Update Email\n " +
                            "3.Update EmployeeId\n " +
                             "4.Update PhoneNumber\n " +
                            "5.Update DateOfBirth\n " +
                            "6.Update DateOfJoining\n ");

            int choose = Convert.ToInt32(Console.ReadLine());

            switch(choose)
            {
                case 1:
                   
                    try
                    {
                       
                        string ID = employeeProject.AddEmployeeID();
                        connection = new SqlConnection(@"Data Source = RANJITH\MSSQLSERVERR; Initial Catalog = Employeee; Integrated Security = True");
                        
                        SqlCommand command = new SqlCommand("UPDATE Employee SET   EmployeeName ='" + employeeProject.AddEmployeeName() + "'WHERE EmployeeId ='" + ID + "';", connection);
                        
                       
                        connection.Open();
                         
                        command.ExecuteNonQuery();
                        Console.WriteLine("Record Deleted Successfully \n");
                    }
                    catch (Exception e)
                    {
                        Console.WriteLine("OOPs, something went wrong.\n" + e);
                    }
             
                    finally
                    {
                        connection.Close();
                    }

                    break;
                case 2:
                    
                    try
                    {
                     
                        string ID = employeeProject.AddEmployeeID();
                        connection = new SqlConnection(@"Data Source = RANJITH\MSSQLSERVERR; Initial Catalog = Employeee; Integrated Security = True");

                        SqlCommand cm = new SqlCommand("UPDATE Employee SET   Email ='" + employeeProject.AddEmail() + "'WHERE EmployeeId ='" + ID + "';", connection);

                        connection.Open();

                        cm.ExecuteNonQuery();
                        Console.WriteLine("Record Deleted Successfully \n");
                    }
                    catch (Exception e)
                    {
                        Console.WriteLine("OOPs, something went wrong.\n" + e);
                    }

                    finally
                    {
                        connection.Close();
                    }

                    break;
                case 3:
                    try
                    {
                        
                        string Email = employeeProject.AddEmail();
                        connection = new SqlConnection(@"Data Source = RANJITH\MSSQLSERVERR; Initial Catalog = Employeee; Integrated Security = True"); 
                        SqlCommand cm = new SqlCommand("UPDATE Employee SET   EmployeeId ='" + employeeProject.AddEmployeeID() + "'WHERE Email ='" + Email + "';", connection);
                        connection.Open();
                        cm.ExecuteNonQuery();
                        Console.WriteLine("Record Deleted Successfully \n");
                    }
                    catch (Exception e)
                    {
                        Console.WriteLine("OOPs, something went wrong.\n" + e);
                    }

                    finally
                    {
                        connection.Close();
                    }

                    break;
                case 4:
                    try
                    {
                    
                        string ID = employeeProject.AddEmployeeID(); ;
                        connection = new SqlConnection(@"Data Source = RANJITH\MSSQLSERVERR; Initial Catalog = Employeee; Integrated Security = True");
                        SqlCommand cm = new SqlCommand("UPDATE Employee SET  PhoneNumber ='" +employeeProject.AddEmployeePhoneNumber()+ "'WHERE EmployeeId ='" + ID + "';", connection);
                        connection.Open();

                        cm.ExecuteNonQuery();
                        Console.WriteLine("Record Deleted Successfully \n");
                    }
                    catch (Exception e)
                    {
                        Console.WriteLine("OOPs, something went wrong.\n" + e);
                    }

                    finally
                    {
                        connection.Close();
                    }


                    break;
                case 5:
                    try
                    {
                      
                        string ID = employeeProject.AddEmployeeID(); ;
                        connection = new SqlConnection(@"Data Source = RANJITH\MSSQLSERVERR; Initial Catalog = Employeee; Integrated Security = True");

                        SqlCommand cm = new SqlCommand("UPDATE Employee SET   DateOfBirth ='" + employeeProject.AddDateOfBirth() + "'WHERE EmployeeId ='" + ID + "';", connection);
                        connection.Open();

                        cm.ExecuteNonQuery();
                        Console.WriteLine("Record Deleted Successfully \n");
                    }
                    catch (Exception e)
                    {
                        Console.WriteLine("OOPs, something went wrong.\n" + e);
                    }

                    finally
                    {
                        connection.Close();
                    }
                    break;
                case 6:
                    try
                    {
                      
                        string ID = employeeProject.AddEmployeeID(); ;
                        connection = new SqlConnection(@"Data Source = RANJITH\MSSQLSERVERR; Initial Catalog = Employeee; Integrated Security = True");
                        SqlCommand cm = new SqlCommand("UPDATE Employee SET   DateOfjoin ='" + employeeProject.AddDateOfJoining() + "'WHERE EmployeeId ='" + ID + "';", connection);

                        connection.Open();

                        cm.ExecuteNonQuery();
                        Console.WriteLine("Record Deleted Successfully \n");
                    }
                    catch (Exception e)
                    {
                        Console.WriteLine("OOPs, something went wrong.\n" + e);
                    }

                    finally
                    {
                        connection.Close();
                    }
                    break;
                   
                default:
                    Console.WriteLine("Enter Valid InPut \n");
                   
                    break;
            }
        }
    }
}
