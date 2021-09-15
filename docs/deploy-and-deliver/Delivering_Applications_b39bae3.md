<!-- loiob39bae31d35d4d039431973116363d57 -->

# Delivering Applications

There are several options for propagating developed applications from one subaccount to another, for example, from your Development to your Testing and Production subaccounts.


<table>
<tr>
<th>

Delivery Option \(Tool Support and Automation Decreasing from Top to Bottom\)



</th>
<th>

Development content \(such as Java, HTML5, SAP HANA XSA\)



</th>
<th>

SAP Integration packages



</th>
<th>

Other app-specific content



</th>
<th>

SAP HANA XS



</th>
<th>

Portal Site



</th>
</tr>
<tr>
<td>

CI/CD



</td>
<td>

recommended



</td>
<td>

n/a



</td>
<td>

n/a



</td>
<td>

recommended for SAP HANA XSA



</td>
<td>

partly possible



</td>
</tr>
<tr>
<td>

Transport Management service with the option to integrate into Change Management \(ChaRM or QGM of SAP Solution Manager\)



</td>
<td>

recommended, but only possible as MTA



</td>
<td>

recommended, but only possible as MTA



</td>
<td>

recommended



</td>
<td>

recommended



</td>
<td>

recommended, but only possible as MTA



</td>
</tr>
<tr>
<td>

CTS+ with the option to integrate into Change Management \(ChaRM or QGM of SAP Solution Manager\)



</td>
<td>

recommended, but only possible as MTA



</td>
<td>

recommended, but only possible as MTA



</td>
<td>

n/a



</td>
<td>

recommended



</td>
<td>

recommended, but only possible as MTA



</td>
</tr>
<tr>
<td>

SAP HANA Application Lifecycle Management



</td>
<td>

n/a



</td>
<td>

n/a



</td>
<td>

n/a



</td>
<td>

recommended for SAP HANA XSC



</td>
<td>

n/a



</td>
</tr>
<tr>
<td>

Manually



</td>
<td>

possible



</td>
<td>

possible



</td>
<td>

recommended, but with app-specific procedures



</td>
<td>

possible



</td>
<td>

possible



</td>
</tr>
</table>

-   Choose your SAP solution for continuous integration and delivery.

    At the moment, SAP offers three solutions for applying CI/CD in your software development. Depending on your expertise in CI/CD, the level of flexibility you wish, and the infrastructure you bring \(or don’t bring\) along, choose one of the following options:

    <a name="loiob39bae31d35d4d039431973116363d57__table_k4x_kts_hnb"/>SAP Solutions for Continuous Integration and Delivery


    <table>
    <tr>
    <th>

    CI/CD Solution


    
    </th>
    <th>

    Required Expertise in CI/CD


    
    </th>
    <th>

    Level of Flexibility


    
    </th>
    <th>

    Infrastructure


    
    </th>
    </tr>
    <tr>
    <td>

     **[SAP Continuous Integration and Delivery](https://help.sap.com/viewer/product/CONTINUOUS_DELIVERY/Cloud/en-US)** 


    
    </td>
    <td>

    Low


    
    </td>
    <td>

    Low


    
    </td>
    <td>

    SAP Continuous Integration and Delivery is ready to use and doesn’t need a separate CI/CD infrastructure.


    
    </td>
    </tr>
    <tr>
    <td>

     **[Project "Piper"](https://sap.github.io/jenkins-library/)** 


    
    </td>
    <td>

    Medium


    
    </td>
    <td>

    Medium


    
    </td>
    <td>

    Project "Piper" requires Jenkins as underlying CI/CD infrastructure. If you don’t have a Jenkins instance, yet, use the Cx Server to bootstrap a preconfigured one. See [Getting Started with Project "Piper"](http://help.sap.com/disclaimer?site=https://sap.github.io/jenkins-library/guidedtour/).


    
    </td>
    </tr>
    <tr>
    <td>

     **[Continuous Integration and Delivery Best Practices Guide](https://help.sap.com/viewer/3324745951b44b578bd65221d2ff8f9a/Cloud/en-US)** 


    
    </td>
    <td>

    High


    
    </td>
    <td>

    High


    
    </td>
    <td>

    The CI/CD Best Practices guide requires an existing infrastructure on any CI/CD stack.


    
    </td>
    </tr>
    </table>
    
    For more information, see [SAP Solutions for Continuous Integration and Delivery](https://help.sap.com/viewer/8cacec64ed854b2a88e9a0973e0f97a2/Cloud/en-US/e9fa320181124fa9808d4446a1bf69dd.html) and [Which SAP Solution for CI/CD Meets Your Needs?](https://help.sap.com/viewer/8cacec64ed854b2a88e9a0973e0f97a2/Cloud/en-US/e9fa320181124fa9808d4446a1bf69dd.html#loioa49d1ba1ecef4e9d96deffd127c4522d).

-   If you're building an extension to SAP S/4HANA, consider using the continuous delivery toolkit that's provided with the SAP Cloud SDK. The toolkit helps you manage the infrastructure and provides a ready-to-use continuous delivery pipeline out-of-the-box. It includes the following freely available components:

    -   Maven project archetypes for rapidly creating a new SAP S/4HANA extension application along best practices
    -   A preconfigured Jenkins CI and CD server that is managed via easy-to-use lifecycle scripts and Docker images
    -   A ready-to-use pipeline for building, testing, quality checking, and deploying applications that have been created from the SAP Cloud SDK archetypes without writing any pipeline code
    For more information, see [SAP Cloud SDK](https://developers.sap.com/topics/s4hana-cloud-sdk.html).

-   If you want to have more control, especially when propagating changes towards your production environment, consider the following transport management options:
    -   For cloud transports, also in hybrid landscapes: the **SAP Cloud Transport Management** service, which allows you to transport content archives, delivery units of SAP HANA XS classic model, and application-specific content, such as SAP BTP Integration content, between different subaccounts, which might also reside in different global accounts, spread across different regions. This service might be especially suitable if you don't have an ABAP-based landscape, don't want to involve on-premise ABAP systems in your scenario, or have to handle SAP BTP application-specific content, independent of whether it is provided as multitarget application files or in other formats.

        For more information, see [SAP Transport Management Service](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US).

    -   For ABAP-centric or hybrid scenarios, the **enhanced Change and Transport System \(CTS+\)**, running in an on-premise ABAP system. Besides handling the transport of on-premise systems \(such as of ABAP and Java artifacts\), CTS+ also lets you transport SAP BTP artifacts from one subaccount to another. However, this is only supported if the artifacts are packaged as multitarget application archives. Please note that no other SAP BTP content format is planned to be supported by CTS+.

        For more information, see [Transporting Multitarget Applications with CTS+](https://help.sap.com/viewer/663f91a6573b49ae9fa5f0007abb4d18/Internal/en-US/f598f69a9be347029b7e5e7205fc7d1f.html "You can enable transport of SAP BTP applications and application content that is available as Multitarget Applications (MTA) using the Enhanced Change and Transport System (CTS+).") :arrow_upper_right:.

    -   Both CTS+ and SAP BTP Transport Management allow an integration into change management approaches around SAP Solution Manager. You can either run CTS+ centrally on SAP Solution Manager and integrate it with change management tools, such as Change Request Management \(ChaRM\) or Quality Gate Management – or you can integrate SAP BTP Transport Management service into these tools running on SAP Solution Manager \(minimum version: SAP Solution Manager 7.2 SP10\). It is even possible to use CTS+ and SAP BTP Transport Management service in parallel within ChaRM or QGM.

        With this approach, you can set up synchronized transports in hybrid scenarios \(involving both on-premise ABAP content and SAP BTP content\). For more information, see [Interplay of SAP Transport Management, CTS+ and ChaRM in hybrid landscapes](https://blogs.sap.com/2020/01/31/interplay-of-sap-cloud-platform-transport-management-cts-and-charm-in-hybrid-landscapes/).

        Combine CI/CD with transport management \(either in the form of SAP BTP Transport Management service or CTS+\), to gain more control over the delivery of release candidates towards your production environment and at the same time benefit from the agility CI/CD brings to your development. For more information, see [How to integrate SAP Transport Management into your CI/CD pipeline](https://blogs.sap.com/2019/08/20/how-to-integrate-sap-cloud-platform-transport-management-into-your-cicd-pipeline/). It is also possible to combine CI/CD, CTS+, Transport Management and SAP Solution Manager Change Management.

-   **Deploy applications manually** from your IDE to different subaccounts. Import or export your application using the SAP BTP cockpit, or use the Console Client for the Neo environment or the Cloud Foundry command line interface to deploy your application.

    > ### Note:  
    > You can transport portal settings and configurations only by manually redeploying your application in each subaccount.

-   In the Neo environment, consider to use the Solution Export Wizard that you can start in SAP BTP cockpit to model solutions by selecting comprised components \(with an automated resolution of interdependencies\) and to either export the outcome \(as multitarget application file\) or to directly handle the modeled solution via the change management options outlined above. For more information, see [Solution Export Wizard - Ease Modeling and Export of Solutions as MTA](https://blogs.sap.com/2018/08/03/solution-export-wizard-ease-modeling-and-export-of-solutions-as-mta/).

-   \(HTML5 applications only\) **Synchronize Git repositories** and create build scripts that let you transfer commits from the repository of the source subaccount to the repository of the target subaccount. After the synchronization, you must still deploy the application manually using the SAP BTP cockpit.
-   \(SAP HANA XS applications only\) Use the **SAP HANA XS Application Lifecycle Management \(HALM\)** to create transport routes between two SAP HANA systems, then transport delivery units between those systems. For more information, see [SAP HANA Application Lifecycle Management](https://help.sap.com/viewer/52715f71adba4aaeb480d946c742d1f6/2.0.03/en-US/9a012d6438764459a581e6af55a87c46.html).




**Related Information**  


[Blog on Transport Approaches in SAP BTP](https://blogs.sap.com/2017/06/30/part-6-transport-approaches-in-sap-cp/)

