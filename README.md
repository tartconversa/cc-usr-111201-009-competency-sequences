# 课程能力路径的有界间隔序列发现

本项目保存高校公共算力与教学研究的虚构汇总资料和Python读取工具。现有工具仅解析输入并显示类型与记录数，不执行统计计算、优化、拟合或训练。样本不代表真实高校、个人或教学成效。

## 资料口径

activities按学生、课程周期、活动与时刻保存人工标签项集，activity_id相同记录应合并标签；outcomes是预先登记的二元课程结果，不是模型评分。

fixtures为只读资料目录，src/activity_reader.py为现有读取器，material-index.json记录文件内容摘要。研究结果可以放入独立.workspace-output目录，不要覆盖原始数据。

## 运行与开发

Python 3.11及以上版本；现有读取器只用标准库，无安装步骤。进入项目根目录：

    python -m src.activity_reader fixtures/activities.jsonl

编译检查：

    python -m compileall -q src tests

输入契约测试：

    python -m unittest discover -s tests -v

## 容器环境

    docker build -t competency-sequences:local .
    docker run --rm competency-sequences:local

镜像按完整摘要固定，默认执行读取测试。容器不需要访问外部教学平台。
