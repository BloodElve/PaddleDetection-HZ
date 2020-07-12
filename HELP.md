#tools
##train.py
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