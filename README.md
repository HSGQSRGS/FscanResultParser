FscanResultParser
 
FscanResultParser是一款面向安全运维场景的Fscan扫描结果解析工具，采用Python语言开发，以稳定高效易扩展为设计目标，能够快速从Fscan原始扫描日志中提取资产与漏洞数据并生成标准化报表，支持批量文件处理目录递归解析多种编码自动识别结果缓存加速网段与端口精准过滤等实用功能，可一键导出ExcelCSVJSONTXT格式文件，同时生成包含资产分布端口分布网段统计的完整报告，工具全程保持对原生Fscan格式的兼容，具备完善的异常处理机制与日志记录能力，无需复杂配置即可直接投入使用，大幅提升内网资产梳理与漏洞巡检的工作效率
 
核心功能
 
支持批量文件与目录递归解析 自动识别UTF8GBKGB2312Latin1等多种编码避免乱码 精准提取IP端口网段资产信息漏洞信息 支持IP网段CIDR端口范围资产类型黑白名单过滤 内置结果缓存机制重复文件秒级加载 自动去重排序保证数据唯一性 支持ExcelCSVJSONTXT四种输出格式 生成包含资产漏洞网段端口的统计报告 全链路日志监控与异常捕获 命令行参数化配置支持脚本集成运行
 
安装依赖
 
pip install pandas openpyxl
 
使用说明
 
基础解析单个文件 python fscan_excel.py result.txt
批量解析目录 python fscan_excel.py ./scan_logs/
指定导出格式 python fscan_excel.py result.txt -f csv
网段过滤仅保留指定网段 python fscan_excel.py result.txt --include-subnet 192.168.0.0/24
端口过滤仅保留指定端口 python fscan_excel.py result.txt --include-port 80 443 8080
关闭缓存并输出详细日志 python fscan_excel.py result.txt --no-cache -v
生成统计报告 python fscan_excel.py result.txt --report-file report.json
 
输出文件
 
默认生成带时间戳的结果文件 包含资产表漏洞表 支持自定义输出名称与格式 可直接用于汇报归档与进一步数据分析
 
适用场景
 
内网资产梳理与统计 漏洞巡检结果汇总 安全评估报告生成 批量扫描结果自动化处理 安全运维日常数据清洗与报表输出
