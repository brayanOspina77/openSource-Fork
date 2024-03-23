package modeloCliente;

import com.mysql.jdbc.Connection;
import java.util.logging.Level;
import java.util.logging.Logger;
import java.sql.DriverManager;
import java.sql.SQLException;

/**
 *
 * @author braya
 */
public class Conexion {
    
    public static final String url= "jdbc:mysql://localhost:3306/programacompleto?autoreconnect=true&useSSL=false";
    public static final String user= "root";
    public static final String pass= "1031";
    
    public Connection getConnection(){
        
        Connection con = null;
        
        try {
            Class.forName("com.mysql.jdbc.Driver"); 
            con = (Connection) DriverManager.getConnection(url, user, pass);
            System.out.println("Conexion Correcta");
            
            return con;
            
        
        } catch (ClassNotFoundException ex) {
            Logger.getLogger(Conexion.class.getName()).log(Level.SEVERE, null, ex);
        } catch (SQLException ex) {
            Logger.getLogger(Conexion.class.getName()).log(Level.SEVERE, null, ex);
        }
        
        return null;
       
        
    }
    
}
