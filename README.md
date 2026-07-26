# Logstash log parsing configuration file
Logstash là một thành phần quan trọng trong giải pháp SIEM ELK Stack của Elastic. Trong repo này, có 4 tệp cấu hình xử lý log từ Linux log:
1. 00-input-beats.conf: Cấu hình đầu vào của Logstash là các beat (Winlogbeat, Filebeat,...).
2. 20-ubuntu-auth.conf: Cấu hình cách xử lý authentication log của Linux. Hiện tại, tệp này chỉ xử lý các dòng log có chứa "Failed password" ứng với các lần đăng nhập thất bại bằng SSH.
3. 25-ubuntu-auditd.conf: Cấu hình cách thức xử lý từng dòng audit log.
4. 99-output-elasticsearch.conf: Cấu hình đầu ra của Logstash là Elasticsearch.

Kết quả thu được là các dòng log đã được xử lý thành nhiều trường (field) theo đặc tả ECS (Elastic Common Schema) như event.action, event.category, process.args, process.command_line,...
