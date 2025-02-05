<!-- loio8eef9590a1d24e87af239d7c7e15fffe -->

# Memory Calculator V2



<a name="loio8eef9590a1d24e87af239d7c7e15fffe__section_ytm_f2x_42b"/>

## Customization

Customize the memory options by using the `JBP_CONFIG_JAVA_OPTS` environment variable:

```
---
applications:
- name: <app-name>
  ...
  env:
    JBP_CONFIG_JAVA_OPTS: "[java_opts: '-Xms144M -Xss3M -Xmx444444K -XX:MetaspaceSize=66666K -XX:MaxMetaspaceSize=88888K']"
```

The *memory\_calculator\_v2* section in the [config/sapjvm.ym](memory-calculator-v1-sap-jvm-memory-calculator-c1059e0.md#loioc1059e056aad406297addcd177a4fb7c__sap-samplecodeblock_ob1_fnk_r2b) configuration file has three sizing options:

-   `stack_threads` – an estimate of the number of threads that will be used by the application
-   `class_count` – an estimate of the number of classes that will be loaded
-   `headroom` – percentage of total memory available that is unallocated to cover JVM overhead

You can customize the three memory options by using the following environment variables:

```
---
applications:
- name: <app-name>
  ...
  env:
    JBP_CONFIG_SAPJVM: "[memory_calculator_v2: {stack_threads: 266, class_count: 1001, headroom: 5}]"
    JBP_CONFIG_COMPONENTS: "jres: ['com.sap.xs.java.buildpack.jdk.SAPMachineJDK']"
    JBP_CONFIG_SAP_MACHINE_JDK: "[memory_calculator_v2: {stack_threads: 266, class_count: 1001, headroom: 5}]"
```

**Related Information**  


[GitHub: Java Buildpack Memory Calculator](https://github.com/cloudfoundry/java-buildpack-memory-calculator)

