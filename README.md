# 🚀 Lightweight Spring Actuator Monitor

A zero-setup HTML dashboard for monitoring Spring Boot Actuator metrics in real-time. 
Download, open in your browser, and start monitoring immediately.

This standalone dashboard transforms raw Actuator endpoints into an intuitive interface with live metrics, progress bars, 
and detailed explanations of what each metric means and when to take action. 
Perfect for development, debugging, and learning about JVM performance without the complexity of enterprise monitoring stacks.

## 🎯 Why This Project Exists

This dashboard was created to fill a specific need for a monitoring solution that balances simplicity with detailed insight. 
While many tools exist, they often fall short in one of these key areas:

**Simplicity and Zero-Friction Deployment**: Unlike enterprise monitoring stacks (Spring Boot Admin, Prometheus, Grafana, ELK), 
there's no infrastructure to set up, no configuration files to maintain, and no learning curve. 
It's a single HTML file that works anywhere—from local development to quick production troubleshooting.

**Transparency and Trust**: As a lightweight, open-source solution with readable code, developers can understand exactly 
how it works, customize it for their needs, and contribute improvements. No black boxes, no vendor lock-in, no hidden costs.

**Educational Value with Actionable Insights**: While tools like Spring Boot Admin show you the metrics, this dashboard 
explains what they mean, when to be concerned, and how to optimize. Each metric comes with context, thresholds, 
and practical JVM tuning advice—turning monitoring into a learning experience.

Whether you're debugging memory issues during development, demonstrating JVM behavior in a workshop, or need quick insights 
without spinning up a full monitoring stack, this tool bridges the gap between "too simple" and "too complex."

Perfect for developers who value pragmatic solutions over enterprise complexity.

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
