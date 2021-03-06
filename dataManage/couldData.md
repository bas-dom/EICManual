### 云数据

云数据页面主要功能如下：

1. 点击类型选择，显示下拉框，包含了现场点、虚拟点、计算点。选择任意一个类型，表格就会展示对应类型的数据。

2. 点击新建，显示下拉框，可以选择新建虚拟点、新建计算点： 1. 点击虚拟点：弹出新建虚拟点的窗口，点名 、初始点值 两个输入框是必填的，点释义可以选填。如果不填写，新建虚拟点将无法完成。确认信息填写完成无误后，点击创建。如果创建成功，则提示虚拟点创建成功。 2. 点击计算点：弹出新建计算点的窗口，点名、计算脚本 是必填的，计算脚本的内容就是写一段计算规则的代码，如：

   1. ```
      def main():
          if get_act_time().minute<10:
              if get_last_update_delta_minutes_of_this_point()>30:
                  x = get_avg_data_of_last_hour('bjjw_18_t')
              else:
                  x = get_last_value()
              return round(x,1) if x else x
          else:
              return None
      ```

      并且确保计算脚本填写正确，然后再点击在线测试，右侧的脚本执行信息框才会显示执行脚本的内容。不然会提示错误信息。并且信息框会处于loading状态。最后点击创建计算点。创建完成后会提示成功信息。

3. 删除：选择一个或者多个点位，点击删除，弹出确认提示框，如果确认删除，则**数据将不能会恢复。**

4. 修改：选择一个点位，点击修改,如果是虚拟点，则弹出修改虚拟点的窗口，计算点则弹出计算点的窗口。修改的规则可参考新建点位。

5. 搜索：可以根据输入的点位模糊搜索符合条件的点，如点位 bjjw\_18\_t\_avg 可以通过bj或者BJ搜索，可以搜索包含对应字符的点并且不区分大小写。

6. 点击同步现场点位，将现场点同步到页面显示。

7. 选择一个点位，点击趋势，可以弹出历史曲线图。具体规则可参考 [原始数据](/dataManage/originData.md) 内的趋势说明。



