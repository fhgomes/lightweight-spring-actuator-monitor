# 🚀 Lightweight Spring Actuator Observer

A simple, lightweight HTML dashboard for monitoring Spring Boot Actuator metrics in real-time. No installation required - just open in your browser!

This project provides a lightweight, standalone HTML dashboard designed specifically for monitoring Spring Boot Actuator metrics. It offers a user-friendly web interface that displays application health and performance data with real-time updates and detailed explanations for each metric. The dashboard is built to be a simple, plug-and-play solution that requires no complex setup.

## 🎯 Motivation & Value
This dashboard was created to fill a specific need for a monitoring solution that balances simplicity with detailed insight. While many tools exist, they often fall short in one of these key areas:

Simplicity and Accessibility: Unlike heavy, complex monitoring stacks like Prometheus and Grafana, this project requires no additional infrastructure or learning curve. It's a single, easily deployable artifact.

Trust and Transparency: As a free and open-source solution, it provides complete transparency, allowing developers to audit the code and build confidence in its security and reliability.

Deeper Insights: It goes beyond basic dashboards like the default Spring Boot Admin, offering more detailed explanations and context for each metric. This helps developers and operators not only see what's happening but also understand why and what action to take.

## ✨ Features

- **Real-time monitoring** of JVM memory, CPU, and GC metrics
- **Zero dependencies** - pure HTML/CSS/JavaScript
- **Auto-refresh** with configurable intervals
- **Detailed explanations** for each metric with optimization tips
- **Responsive design** that works on desktop and mobile
- **Easy setup** - just point to your Spring Boot application

## 📊 Supported Metrics

- **Memory**: Heap Used/Max, Non-Heap Usage
- **Performance**: CPU Usage, Live Threads
- **Garbage Collection**: Memory Allocated
- **Progress bars** showing memory utilization

## 🚀 Quick Start

1. **Download** the HTML file from this repository
2. **Open** it in any modern web browser
3. **Configure** your Spring Boot application URL (default: http://localhost:8080)
4. **Click Connect** and start monitoring!

### Prerequisites

Your Spring Boot application needs to have Actuator enabled:

```yaml
management:
  endpoints:
    web:
      exposure:
        include: health,metrics
  endpoint:
    health:
      show-details: always
```

## 🎯 Use Cases

- **Development** monitoring during local testing
- **Quick debugging** of memory issues
- **Learning** about JVM metrics and their meanings
- **Lightweight alternative** to heavy monitoring solutions
- **Demo purposes** for Spring Boot applications

## 📱 Screenshots

*Coming soon - add screenshots of the dashboard here*

## 🔧 Configuration

The dashboard automatically detects and displays:
- JVM Memory metrics (heap/non-heap)
- System CPU usage
- Thread information
- Garbage Collection statistics

Simply change the "Actuator URL" field to point to your Spring Boot application.

## 🤝 Contributing

Contributions are welcome! Please see our [CONTRIBUTING.md](CONTRIBUTING.md) for details.

### Quick Contribution Steps
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Support

- **Issues**: Report bugs or request features via [GitHub Issues](https://github.com/fhgomes/lightweight-spring-actuator-observer/issues)
- **Discussions**: Join conversations in [GitHub Discussions](https://github.com/fhgomes/lightweight-spring-actuator-observer/discussions)

## ⭐ Show Your Support

If this project helped you, please consider giving it a star! ⭐

## 🔗 Related Projects

- [Spring Boot Actuator](https://docs.spring.io/spring-boot/docs/current/reference/html/actuator.html)
- [Spring Boot Admin](https://github.com/codecentric/spring-boot-admin)
- [Micrometer](https://micrometer.io/)

---

**Made with ❤️ for the Spring Boot community**

---

**Creator:** [fhgomes](https://github.com/fhgomes/fhgomes)  
**Contact:** tech.fernando.gomes@gmail.com
