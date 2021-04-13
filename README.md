version: '2'
services:
  python:
    image: kammana/python-redis:1
    container_name: python
    environment:
      - "redis_host=redis"
    ports:
     - "8080:5000"
    networks:
      - javahome-app
  redis:
    container_name: redis
    image: "redis"
    networks:
      - javahome-app
networks:
  javahome-app:
    driver: bridge
