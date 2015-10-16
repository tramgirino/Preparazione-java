
public class TrafficLigths extends thread{

	private LightState state= new GreenState();
	public void change(){ state.changestate(this);} 
	public void show(){	Sytem.out.println(state.color());}
	public void wait(){sleep(state.length());}
	public static void main(String[] args) {
		TrafficLigths t1=new TrafficLigths();
		while(true){ t1.show();t1.wait();t1.change();}
	}

}

public class GreenState extends TrafficLigths {
	public void show(){
		System.out.println("green");
	}
	public void wait(){
		sleep(30);
	}
	public void change(){
		state.change(YellowState);
	}
}

public class RedState extends TrafficLigths{
	public void show(){	System.out.println("red"); }
	public void wait(){ sleep(40); }
	public void change(){state.change(YellowState);	}
}
