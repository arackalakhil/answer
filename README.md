

1)Write a regex to extract all the numbers with orange color background from the below text in italics (Output should be a list).


{"orders":[{"id":1},{"id":2},{"id":3},{"id":4},{"id":5},{"id":6},{"id":7},{"id":8},{"id":9},{"id":10},{"id":11},{"id":648},{"id":649},{"id":650},{"id":651},{"id":652},{"id":653}],"errors":[{"code":3,"message":"[PHP Warning #2] count(): Parameter must be an array or an object that implements Countable (153)"}]}

## Answer<br />
import re<br />
text = '{"orders":[{"id":1},{"id":2},{"id":3},{"id":4},{"id":5},{"id":6},{"id":7},{"id":8},{"id":9},{"id":10},{"id":11},{"id":648},{"id":649},{"id":650},{"id":651},{"id":652},{"id":653}],"errors":[{"code":3,"message":"[PHP Warning #2] count(): Parameter must be an array or an object that implements Countable (153)"}]}'
numbers = re.findall(r'(?<=:)\d+', text)<br />
print(numbers)<br />



output will be ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '648', '649', '650', '651', '652', '653', '3']<br />

## <br />
2. Write and share a small note about your choice of system to schedule periodic tasks (such as downloading a list of ISINs every 24 hours). Why did you choose it? Is it reliable enough; Or will it scale? If not, what are the problems with it? And, what else would you recommend to fix this problem at scale in production?<br />



There are several options available for scheduling periodic tasks in a Python/Django application, some of which include:<br />

Celery: This is a powerful task queue that can be used to schedule periodic tasks. It is built on top of the message broker, such as RabbitMQ or Redis, which makes it reliable and able to scale to handle a large number of tasks. It also provides a web interface for monitoring and managing tasks.<br />

Apscheduler: This is a lightweight library for scheduling tasks. It is easy to use and can be integrated into a Django application with minimal setup. It can be used to schedule tasks with a specific interval or at a specific time.<br />

Cron: This is a standard Linux utility for scheduling tasks. It can be used to schedule tasks to run at specific intervals. It is reliable and can be used to schedule tasks on a production server.<br />
Celery is more robust and can handle a large number of tasks and also provides a web interface for monitoring and managing tasks. Celery can also be integrated with Django very well.If this solution doesn't scale as per the requirement, one can consider using a load balancer to distribute the tasks among multiple worker servers. Additionally, one can also consider using a message broker that can handle a large number of tasks such as Kafka or Rabbitmq
## <br />

