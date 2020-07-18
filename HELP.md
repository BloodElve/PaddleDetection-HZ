#Code Document
##tools
###train.py
| 参数名 | 简写 | 默认值 | 作用 |
| :-----| :---- | :---- | :---- |
| --config | -c |  | configuration file to use |
| --opt | -o |  | configuration file to use |
| --resume_checkpoint | -r | None | Checkpoint path for resuming training |
| --fp16 |  | False | Enable mixed precision training |
| --loss_scale |  | 8. | Mixed precision training loss scale |
| --eval |  | False | Whether to perform evaluation in train |
| --output_eval |  | 8. | Evaluation directory, default is current directory |
| --use_vdl |  | False | whether to record the data to VisualDL |
| --vdl_log_dir |  | vdl_log_dir/scalar | VisualDL logging directory for scalar |
| --enable_ce |  | False | If set True, enable continuous evaluation job |
| --is_profiler |  | 0 | The switch of profiler tools. (used for benchmark) |
| --profiler_path |  | ./detection.profiler | The profiler output file path. (used for benchmark) |
##ppdet
###core
####workspace.py
| 类 | 作用 |
| :---- | :---- |
| AttrDict(dict) | 简单封装字典 |

| 方法 | 参数 | 返回值 | 作用 |
| :---- | :---- | :---- | :---- |
| merge_config(config, another_cfg=None) | *config 配置文件字典 *another_cfg 配置文件字典 | *another_cfg 缺省时为全局变量global_config | 合并两配置文件字典 |
| dict_merge(dct, merge_dct) | *dct 配置文件字典 *merge_dct 配置文件字典 | *dct | merge_config真正用于合并配置文件字典的方法 |
| load_config(file_path) | *file_path 配置文件绝对路径 | *global_config 全局配置 | 加载配置文件，_READER_用于加载基础reader.yml配置文件,原配置文件内容覆盖reader.yml内容 |
| create(cls_or_name, **kwargs) | *cls_or_name 类名 | *cls(**kwargs) 根据类名创建的实例| 根据类名创建实例 |
| register(cls) | *cls 类 | *cls | 帮助神经网络相关类注册入global_config（装饰器此处用法为扩充类功能） |
####config
#####schema.py
| 类 | 作用 |
| :---- | :---- |
| SchemaDict(dict) | 用于封装神经网络配置 |

| 方法 | 参数 | 返回值 | 作用 |
| :---- | :---- | :---- | :---- |
| extract_schema(cls) | *cls 类 | *schema 神经网络配置文件字典 | 根据类将神经网络配置注册入global_config |
###utils
####check.py
| 方法 | 参数 | 返回值 | 作用 |
| :---- | :---- | :---- | :---- |
| check_config(cfg) | *cfg 配置文件字典 | *cfg | *检查architecture,num_classes是否存在 *若无log_iter，设置为20 *TrainReader和EvalReader和TestReader中dataset.with_background一致 |