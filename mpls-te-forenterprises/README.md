## 1. The Problem
  * Link State IGP's use SPF
    * path selection is based on cost
    * when is cost not sufficient?
  
## 2. Principles of Traffic Engineering
  * CSPF
  * RSVP
    * roots in QoS
      * resource conflict arbitration vs. conflict avoidance
      * hop-by-hop reservation system
    * with TE, hosts do not participate in RSVP, only routers
  * Where is the state located?
    * Hard state refresh vs. Soft state refresh
  * IGP modifications
    * TE database
  * What is a TE Tunnel?
    * representation of an LSP
      * unidirectional
      * signalled from the headend

## 3. High-level TE Design

  * strategic
  * tactical
  * fast convergence

## 4. Implementation Example

  * base configuration requirements
    * enabled globally
    * enabled in the IGP
    * for ISIS: metric-style wide
    * TE router-id configured in the IGP
    * TE enabled on appropriate interfaces
    * RSVP enabled on appropriate interfaces

  * IOS-XE configuration example:
```
configuration here
```

  * tunnel requirements
    * tunnel type
    * method for making tail-end routes available via the tunnel
      * you don't run an IGP over the tunnel
    * path option
      * explict path
        * next hop
        * exclude

  * IOS-XE configuration example:
```
configuration here
```

## 5. Use Cases
  * Most use cases will involve using a private backbone of some sort
  * Case 1: 1 odd duck link (strategic)
  * Case 2: New nontransit datacenter (strategic)
  * Case 3: Transition from IPSec VPN over Internet to private backbone (tactical or strategic)
  
## 6. Further Reading
  * Books
    * Traffic Engineering with MPLS (Osborne and Simha, Cisco Press)
      * https://www.safaribooksonline.com/library/view/traffic-engineering-with/1587050315/
    * MPLS-Enabled Applications (Minei and Lucek, Wiley)
      * https://www.safaribooksonline.com/library/view/mpls-enabled-applications-emerging/9780470976135/
  * Docs and Blogs
    * https://www.cisco.com/c/dam/en/us/products/collateral/ios-nx-os-software/multiprotocol-label-switching-archive/prod_white_paper0900aecd803128b9.pdf
    * https://www.youtube.com/watch?v=1cD8w4H-eKE
    * http://blog.ipspace.net/2008/09/do-you-need-ldp-with-mpls-te.html
    * https://www.cisco.com/c/en/us/support/docs/multiprotocol-label-switching-mpls/mpls/29828-mplsvpnte.html
    * https://learningnetwork.cisco.com/thread/117654
    * http://lostintransit.se/2014/08/24/a-quick-look-at-mpls-te/
