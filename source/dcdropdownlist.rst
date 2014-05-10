DcDropDownList控件
==================

DcControl.dll文件添加到VS工具箱，再从工具箱中拉动控件到页面，完成创建控件。

 .. figure:: /_static/listpage.jpg

**方法:**

 * SetData()

   + DataTable绑定数据，DataTable是一个由三列组成的数据表包含ID列、ParentID列、名称列，设定一级ParentID值，AppendListItems 绑定静态项，SelectedId 下拉菜单选中值。
  
   + List绑定数据，AppendListItems 绑定静态项，SelectedId 下拉菜单选中值。


**示例:**

 .. code-block:: C#
    :linenos:
	
    private void DataBind()
    {
	    List<DcControl.DataList> lists = new List<DcControl.DataList>();

	    List<DcControl.DataList.optgroupChild> dlcs = new List<DcControl.DataList.optgroupChild>();
	    dlcs.Add(new DcControl.DataList.optgroupChild()
	    {
            ItemValue = "1",
            ItemText = "北京"
	    });
	    lists.Add(new DcControl.DataList()
	    {
            optgroupText = "北京市",
            child = dlcs
	    });

	    dlcs = new List<DcControl.DataList.optgroupChild>();
	    dlcs.Add(new DcControl.DataList.optgroupChild()
	    {
            ItemValue = "2",
            ItemText = "广州市"
	    });
	    dlcs.Add(new DcControl.DataList.optgroupChild()
	    {
            ItemValue = "2",
            ItemText = "深圳市"
	    });
	    lists.Add(new DcControl.DataList()
	    {
            optgroupText = "广东省",
            child = dlcs
	    });

	    DcDropDownList1.SetData(lists, new ListItem("请选择", "0"), 0);
    }
	
 .. figure:: /_static/dropdownlist.jpg
 
**安装:**
   
 * NuGet: https://www.nuget.org/packages/DcControls/

 * CSDN: https://code.csdn.net/winsty2008/dchelper/tree/master/DcControl/DcDropDownList.cs