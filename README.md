# CommandLine
Creating .jar file
import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;

public class CommandLineJarFile {
    public static void main(String[] args) {
        commandLine(args);
    }
    private static void Time() {
        DateFormat dateFormat = new SimpleDateFormat("yyyy/MM/dd HH:mm:ss");
        Date date = new Date();
        System.out.println(dateFormat.format(date));
    }

    private static void Help() {
        System.out.println("T or t = Time");
        System.out.println("H or Help = Help");
        System.out.println("M or Memory = Memory");
    }

    private static void Memory() {
        int mb = 1024 * 1024;
        // get Runtime instance
        Runtime instance = Runtime.getRuntime();
        System.out.println("***** Heap utilization statistics [MB] *****\n");
        // available memory
        System.out.println("Total Memory: " + instance.totalMemory() / mb);
        // free memory
        System.out.println("Free Memory: " + instance.freeMemory() / mb);
        // used memory
        System.out.println("Used Memory: "
                + (instance.totalMemory() - instance.freeMemory()) / mb);
        // Maximum available memory
        System.out.println("Max Memory: " + instance.maxMemory() / mb);
    }

    private static void commandLine(String[] args) {
        for (String arg : args) {
            switch (arg) {
                case "T":
                case "t":
                    Time();
                    break;
                case "H":
                case "Help":
                    Help();
                    break;
                case "M":
                case "Memory":
                    Memory();
                    break;
            }
        }
    }
}
