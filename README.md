<img align="right" width="250" height="47" src="media/Gematik_Logo_Flag.png"/> <br/>

# OSPO Resources

A resource library providing license templates and configurations for gematik projects. This library serves as a license resolver for the License Maven Plugin.
Additionally this library provides the policy and security templates for the Open Source Program Office (OSPO) of gematik GmbH.

## Purpose

The `ospo-resources` library centralizes license templates resources (Apache, EUPL 1.2) by providing:
- Header templates
- Full license texts
- License resolver configuration
- Policy and security templates
- Contributing guide
- Code of conduct

## Project Structure

```
ospo-resources/
├── src/
│   └── main/
│       └── resources/
│           └── codeofconduct/                  # Code of conduct
│               └── default/                    # Default code of conduct
│                   └── CODE_OF_CONDUCT.md
│               └── <team>/                     # project/team specific code of conduct
│                   └── CODE_OF_CONDUCT.md
│           └── contributing/                   # Contributing guide
│               └── default/                    # Default contributing guide
│                   └── CONTRIBUTING.md
│               └── <team>/                     # project/team specific contributing guide
│                   └── CONTRIBUTING.md
│           └── copyright-header/               # Root directory for license resolver
│               └── eupl-license/               # EUPL 1.2 specific files
│                   ├── licenses.properties
│                   └── eupl_v1_2/              # EUPL 1.2 specific files
│                       ├── header.txt          # Header template
│                       └── license.txt         # Full license text
│           └── license/                        # Root directory for OSPO-Licenses
│               └── apache20/                   # Apache 2.0 specific files
│                   └── LICENSE.md              # Full license text
│               └── eupl12/                     # EUPL 1.2 specific files
│                   └── LICENSE.md              # Full license text
│           └── security/                       # Security policy
│               └── default/                    # Default security policy
│                   └── prod/                   # Default security policy for produtive use 
│                       └── SECURITY.md
│                   └── ref/                    # Default security policy for non-produtive use (reference-implementation, poc) 
│                       └── SECURITY.md
│               └── <team>/                     # project/team specific security policy
│                   └── prod/                   # project/team security policy for produtive use 
│                       └── SECURITY.md
│                   └── ref/                    # project/team security policy for non-produtive use (reference-implementation, poc) 
│                       └── SECURITY.md
└── pom.xml
```

## Usage

### License-Maven-Plugin
This library is designed to be used as a dependency in the License-Maven-Plugin configuration. Example usage in a parent POM:
```xml
<plugin>
    <groupId>org.codehaus.mojo</groupId>
    <artifactId>license-maven-plugin</artifactId>
    <dependencies>
        <dependency>
            <groupId>de.gematik</groupId>
            <artifactId>ospo-resources</artifactId>
            <version>1.1.0</version>
        </dependency>
    </dependencies>
</plugin>
```

The actual plugin configuration should be done in your project's parent POM.

### Policy and Security Templates
The policy and security templates are provided in the `src/main/resources/*` directory. The templates are structured by team and environment. 
The default templates are provided in the `default` directory and can be overridden by project or team specific templates.


## Maintenance
When updating this library:
* Update version number in pom.xml
* Test with a sample project before releasing
* Ensure compatibility with existing license plugin configurations

## Security Policy
If you want to see the security policy, please check our [SECURITY.md](.github/SECURITY.md).

## Contributing
If you want to contribute, please check our [CONTRIBUTING.md](.github/CONTRIBUTING.md).

## License
Copyright 2025 gematik GmbH

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.

See the [LICENSE](./LICENSE.md) for the specific language governing permissions and limitations under the License.

## Additional Notes and Disclaimer from gematik GmbH

1. Copyright notice: Each published work result is accompanied by an explicit statement of the license conditions for use. These are regularly typical conditions in connection with open source or free software. Programs described/provided/linked here are free software, unless otherwise stated.
2. Permission notice: Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions::
    1. The copyright notice (Item 1) and the permission notice (Item 2) shall be included in all copies or substantial portions of the Software.
    2. The software is provided "as is" without warranty of any kind, either express or implied, including, but not limited to, the warranties of fitness for a particular purpose, merchantability, and/or non-infringement. The authors or copyright holders shall not be liable in any manner whatsoever for any damages or other claims arising from, out of or in connection with the software or the use or other dealings with the software, whether in an action of contract, tort, or otherwise.
    3. The software is the result of research and development activities, therefore not necessarily quality assured and without the character of a liable product. For this reason, gematik does not provide any support or other user assistance (unless otherwise stated in individual cases and without justification of a legal obligation). Furthermore, there is no claim to further development and adaptation of the results to a more current state of the art.
3. Gematik may remove published results temporarily or permanently from the place of publication at any time without prior notice or justification.
4. Please note: Parts of this code may have been generated using AI-supported technology.’ Please take this into account, especially when troubleshooting, for security analyses and possible adjustments.

## Contact

E-Mail to [OSPO](mailto:ospo@gematik.de?subject=[OSPO]%20ospo-resources)