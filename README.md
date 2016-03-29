# BaseModel
iOS解析Model数据 方便解析字典与数组 以及 map.

例子:

将自己写好的model类继承自BaseModel(例子为[Rcu_Model]);

json数组:


NSArray *jsonArray = @[
@{@"name":@"日光灯带",@"num":@"2",@"lineType":@"Light"},

@{@"name":@"中央空调",@"num":@"3",@"lineType":@"Air"},

@{@"name":@"左窗帘",@"num":@"4",@"lineType":@"Curtain"}];

//将jsonArray解析为model


NSMutableArray *modelArray = [Rcu_Model baseModelObject:jsonArray];

//解析结果

(
"<Rcu_Model: 0x7f9e21c34e40>",
"<Rcu_Model: 0x7f9e21c38c50>",
"<Rcu_Model: 0x7f9e21c38dd0>"
)

//将jsonArray解析为map类型model

NSMutableDictionary *mapModel = [Rcu_Model baseModelObject:jsonArray andKey:@"num"];

//解析结果

{
2 = "<Rcu_Model: 0x7f9e21f0db30>";
3 = "<Rcu_Model: 0x7f9e21fa9a80>";
4 = "<Rcu_Model: 0x7f9e21f60a90>";
}
