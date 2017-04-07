# 阶乘-
public abstract class Component 
{
	public void add(number1) 
	{
		throw new UnsupportedOperationException();
	}

	public void remove(number1 ) 
	{
		throw new UnsupportedOperationException();
	}

	public Component getChild(int i) 
	{
		throw new UnsupportedOperationException();
	}

	public void operation() 
	{
		throw new UnsupportedOperationException();
	}
}
 

Leaf：在组合中表示叶节点对象，叶节点没有子节点。

public class Leaf extends Component
{
	@Override
	public void operation()
	{
		//your code
	}
}
 

Composite：表示参加组合的有子集的对象，并给出树枝构件的行为。

public class Composite extends Component
{
	ArrayList<Component> components = new ArrayList<Component>();
	
	@Override
	public void add(Component component)
	{
		components.add(component);
	}
	
	@Override
	public void remove(Component component)
	{
		components.remove(component);
	}
	
	@Override
	public Component getChild(int i)
	{
		return components.get(i);
	}
	
	@Override
	public void operation()
	{
		for (Component component : components)
		{
			component.operation();
		}
	}
}
 
