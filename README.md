# Use Mermaid to draw figures in your K8s docs contributions 

Mermaid is a package for generating figures using simple text in markdown files. This document explains how you can use Mermaid to draw and include figures in your K8s docs contributions. It includes multiple examples, live-editor references and three methods for generating and embedding Mermaid figures inside your documentation.

The target audience for this document is anybody wishing to learn about Mermaid and/or how to create and add figures to Kubernetes documentation. You need a basic understanding of markdown and how to use Hugo shortcodes. 

## References

- [Mermaid docs](https://mermaid-js.github.io/mermaid/#/)

- [Mermaid live editor](https://mermaid-js.github.io/mermaid-live-editor)

## Why should I use Mermaid?

- Simple, inline code syntax.

- K8s docs and native docsy theme support.

- On-line live editor so you can create and edit figures. 
  
- Live editor generates a link for each figure. You can share this link to collaborate with colleagues on figure creation and editing.

- Figure updates are simple: just open PR and edit the mermaid code in the respective markdown file.

Basically, Mermaid provides a simple, open and transparent method for the community to add, edit and collaborate on figures for new or existing documents.

--- 


## K8s docs Mermaid examples

This section contains examples of Mermaid figures currently included in K8s docs. 

Docs page: [What is Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/#what-is-ingress)

K8s/website file link: [ingress.md](https://github.com/kubernetes/website/blob/main/content/en/docs/concepts/services-networking/ingress.md)

Live-editor link: [figure](https://mermaid-js.github.io/mermaid-live-editor/edit/#eyJjb2RlIjoiZ3JhcGggIExSXG4gIGNsaWVudChbY2xpZW50XSktLiBJbmdyZXNzLW1hbmFnZWQgPGJyPiBsb2FkIGJhbGFuY2VyIC4tPmluZ3Jlc3NbSW5ncmVzc107XG4gIGluZ3Jlc3MtLT58cm91dGluZyBydWxlfHNlcnZpY2VbU2VydmljZV07XG4gIHN1YmdyYXBoIGNsdXN0ZXJcbiAgaW5ncmVzcztcbiAgc2VydmljZS0tPnBvZDFbUG9kXTtcbiAgc2VydmljZS0tPnBvZDJbUG9kXTtcbiAgZW5kXG4gIGNsYXNzRGVmIHBsYWluIGZpbGw6I2RkZCxzdHJva2U6I2ZmZixzdHJva2Utd2lkdGg6NHB4LGNvbG9yOiMwMDA7XG4gIGNsYXNzRGVmIGs4cyBmaWxsOiMzMjZjZTUsc3Ryb2tlOiNmZmYsc3Ryb2tlLXdpZHRoOjRweCxjb2xvcjojZmZmO1xuICBjbGFzc0RlZiBjbHVzdGVyIGZpbGw6I2ZmZixzdHJva2U6I2JiYixzdHJva2Utd2lkdGg6MnB4LGNvbG9yOiMzMjZjZTU7XG4gIGNsYXNzIGluZ3Jlc3Msc2VydmljZSxwb2QxLHBvZDIgazhzO1xuICBjbGFzcyBjbGllbnQgcGxhaW47XG4gIGNsYXNzIGNsdXN0ZXIgY2x1c3RlcjtcbiIsIm1lcm1haWQiOiJ7XG4gIFwidGhlbWVcIjogXCJkZWZhdWx0XCJcbn0iLCJ1cGRhdGVFZGl0b3IiOmZhbHNlLCJhdXRvU3luYyI6dHJ1ZSwidXBkYXRlRGlhZ3JhbSI6ZmFsc2V9) 

Figure:

![ingress figure](images/ingress-figure.svg)

Code:
```mermaid
{{< mermaid >}}
graph LR;
 client([client])-. Ingress-managed <br> load balancer .->ingress[Ingress];
 ingress-->|routing rule|service[Service];
 subgraph cluster
 ingress;
 service-->pod1[Pod];
 service-->pod2[Pod];
 end
 classDef plain fill:#ddd,stroke:#fff,stroke-width:4px,color:#000;
 classDef k8s fill:#326ce5,stroke:#fff,stroke-width:4px,color:#fff;
 classDef cluster fill:#fff,stroke:#bbb,stroke-width:2px,color:#326ce5;
 class ingress,service,pod1,pod2 k8s;
 class client plain;
 class cluster cluster;
{{</ mermaid >}}
```

---

Docs page: [Pod Topology Spread Constraints#node labels](https://kubernetes.io/docs/concepts/workloads/pods/pod-topology-spread-constraints/#node-labels)

K8s/website file link: [ ../docs/concepts/workloads/pods/pod-topology-spread-constraints.md](https://github.com/kubernetes/website/blob/main/content/en/docs/concepts/workloads/pods/pod-topology-spread-constraints.md)

Live-editor link: [figure](https://mermaid-js.github.io/mermaid-live-editor/edit/#eyJjb2RlIjoiZ3JhcGggVEJcbiAgICBzdWJncmFwaCBcInpvbmVCXCJcbiAgICAgICAgbjMoTm9kZTMpXG4gICAgICAgIG40KE5vZGU0KVxuICAgIGVuZFxuICAgIHN1YmdyYXBoIFwiem9uZUFcIlxuICAgICAgICBuMShOb2RlMSlcbiAgICAgICAgbjIoTm9kZTIpXG4gICAgZW5kXG5cbiAgICBjbGFzc0RlZiBwbGFpbiBmaWxsOiNkZGQsc3Ryb2tlOiNmZmYsc3Ryb2tlLXdpZHRoOjRweCxjb2xvcjojMDAwO1xuICAgIGNsYXNzRGVmIGs4cyBmaWxsOiMzMjZjZTUsc3Ryb2tlOiNmZmYsc3Ryb2tlLXdpZHRoOjRweCxjb2xvcjojZmZmO1xuICAgIGNsYXNzRGVmIGNsdXN0ZXIgZmlsbDojZmZmLHN0cm9rZTojYmJiLHN0cm9rZS13aWR0aDoycHgsY29sb3I6IzMyNmNlNTtcbiAgICBjbGFzcyBuMSxuMixuMyxuNCBrOHM7XG4gICAgY2xhc3Mgem9uZUEsem9uZUIgY2x1c3RlcjtcbiIsIm1lcm1haWQiOiJ7XG4gIFwidGhlbWVcIjogXCJkZWZhdWx0XCJcbn0iLCJ1cGRhdGVFZGl0b3IiOmZhbHNlLCJhdXRvU3luYyI6dHJ1ZSwidXBkYXRlRGlhZ3JhbSI6dHJ1ZX0)

Figure:

![pod topo constraint 1](images/pod-topo-constraint-01.svg)

Code:
```mermaid
{{<mermaid>}}
graph TB
   subgraph "zoneB"
       n3(Node3)
       n4(Node4)
   end
   subgraph "zoneA"
       n1(Node1)
       n2(Node2)
   end
 
   classDef plain fill:#ddd,stroke:#fff,stroke-width:4px,color:#000;
   classDef k8s fill:#326ce5,stroke:#fff,stroke-width:4px,color:#fff;
   classDef cluster fill:#fff,stroke:#bbb,stroke-width:2px,color:#326ce5;
   class n1,n2,n3,n4 k8s;
   class zoneA,zoneB cluster;
{{< /mermaid >}}
```
---

Docs page: [Example: OneTopologySpreadConstraint](https://kubernetes.io/docs/concepts/workloads/pods/pod-topology-spread-constraints/#example-one-topologyspreadconstraint) // first figure on this page

K8s/website file link: [ ../docs/concepts/workloads/pods/pod-topology-spread-constraints.md](https://github.com/kubernetes/website/blob/main/content/en/docs/concepts/workloads/pods/pod-topology-spread-constraints.md)

Live-editor link: [figure](https://mermaid-js.github.io/mermaid-live-editor/edit/#eyJjb2RlIjoiZ3JhcGggIEJUXG4gICAgc3ViZ3JhcGggXCJ6b25lQlwiXG4gICAgICAgIHAzKFBvZCkgLS0-IG4zKE5vZGUzKVxuICAgICAgICBuNChOb2RlNClcbiAgICBlbmRcbiAgICBzdWJncmFwaCBcInpvbmVBXCJcbiAgICAgICAgcDEoUG9kKSAtLT4gbjEoTm9kZTEpXG4gICAgICAgIHAyKFBvZCkgLS0-IG4yKE5vZGUyKVxuICAgIGVuZFxuXG4gICAgY2xhc3NEZWYgcGxhaW4gZmlsbDojZGRkLHN0cm9rZTojZmZmLHN0cm9rZS13aWR0aDo0cHgsY29sb3I6IzAwMDtcbiAgICBjbGFzc0RlZiBrOHMgZmlsbDojMzI2Y2U1LHN0cm9rZTojZmZmLHN0cm9rZS13aWR0aDo0cHgsY29sb3I6I2ZmZjtcbiAgICBjbGFzc0RlZiBjbHVzdGVyIGZpbGw6I2ZmZixzdHJva2U6I2JiYixzdHJva2Utd2lkdGg6MnB4LGNvbG9yOiMzMjZjZTU7XG4gICAgY2xhc3MgbjEsbjIsbjMsbjQscDEscDIscDMgazhzO1xuICAgIGNsYXNzIHpvbmVBLHpvbmVCIGNsdXN0ZXI7XG4iLCJtZXJtYWlkIjoie1xuICBcInRoZW1lXCI6IFwiZGVmYXVsdFwiXG59IiwidXBkYXRlRWRpdG9yIjpmYWxzZSwiYXV0b1N5bmMiOnRydWUsInVwZGF0ZURpYWdyYW0iOnRydWV9)

Figure:
![](images/pod-topo-constraint-02.svg)

Code:
```mermaid
{{<mermaid>}}
graph TB
subgraph "zoneB"
   p3(Pod) --> n3(Node3)
   n4(Node4)
end
subgraph "zoneA"
   p1(Pod) --> n1(Node1)
   p2(Pod) --> n2(Node2)
end
 
classDef plain fill:#ddd,stroke:#fff,stroke-width:4px,color:#000;
classDef k8s fill:#326ce5,stroke:#fff,stroke-width:4px,color:#fff;
classDef cluster fill:#fff,stroke:#bbb,stroke-width:2px,color:#326ce5;
class n1,n2,n3,n4,p1,p2,p3 k8s;
class zoneA,zoneB cluster;
{{< /mermaid >}}
```

## Three methods to add Mermaid figures

You have three methods for adding Mermaid figures to K8s docs: Hugo Mermaid shortcode, hybrid Mermaid+SVG and native docsy support. 

The figure below lays out the three methods:
![3 methods](images/3-mermaid-methods.svg)

[Live editor link to the 3 methods figure](https://mermaid-js.github.io/mermaid-live-editor/edit#eyJjb2RlIjoiZmxvd2NoYXJ0IFRCXG4gICAgc3ViZ3JhcGggdGhpcmRbMy4gTmF0aXZlIERvY3N5XVxuICAgIGRpcmVjdGlvbiBUQlxuICAgICAgIFhbIF0gLS4tIFxuICAgICAgIERbVXNlIGxpdmUgZWRpdG9yPGJyPnRvIGNyZWF0ZS9lZGl0IGZpZ3VyZV0gLS0-IFJbY3V0L3Bhc3RlIGNvZGU8YnI-dG8gLm1kIHBhZ2VdXG4gICAgICAgUiAtLT4gRVtXcmFwIG1lcm1haWQgY29kZTxicj5pbiBgYGBtZXJtYWlkYGBgPGJyPmNvZGUgYmxvY2tdXG4gICAgICAgRSAtLT4gRltUZXN0ISFdXG4gICAgZW5kXG5cbiAgICBzdWJncmFwaCBzZWNvbmRbMi4gSHlicmlkIE1lcm1haWQrU1ZHXVxuICAgICAgICBkaXJlY3Rpb24gVEJcbiAgICAgICAgU1sgXSAtLi1cbiAgICAgICAgR1tVc2UgbGl2ZSBlZGl0b3I8YnI-dG8gY3JlYXRlL2VkaXQgZmlndXJlXSAtLT4gSltHZW5lcmF0ZS9kb3dubG9hZCBTVkddXG4gICAgICAgIEogLS0-IEtbQWRkIGxpdmUgZWRpdG9yIGltYWdlPGJyPlVSTCB0byBTVkcgZmlsZTxicj51c2luZyB0ZXh0IGVkaXRvcl1cbiAgICAgICAgSyAtLT4gTFtBZGQgU1ZHIGZpbGUgdG88YnI-ZG9jcyB1c2luZyBzdGFuZGFyZDxicj50ZWNobmlxdWVzXVxuICAgICAgICBMIC0tPiBPW1Rlc3QhIV0gIFxuXG4gICAgZW5kXG5cbiAgICBzdWJncmFwaCBmaXJzdFsxLiBTaG9ydGNvZGVdXG4gICAgZGlyZWN0aW9uIFRCXG4gICAgICAgIFlbIF0gLS4tXG4gICAgICAgIEJbVXNlIGxpdmUgZWRpdG9yPGJyPnRvIGNyZWF0ZS9lZGl0IGZpZ3VyZV0gLS0-IFFbY3V0L3Bhc3RlIGNvZGU8YnI-dG8gLm1kIHBhZ2VdIFxuICAgICAgICBRIC0tPiBDW1dyYXAgbWVybWFpZCBjb2RlPGJyPiBpbiBzaG9ydGNvZGUgdGFnc10gLS0-IFBbVGVzdCEhXVxuICAgIGVuZFxuICAgIFxuICAgIEEoW2ZhOmZhLXVzZXIgQ29udHJpYnV0b3JdKSAtLT4gZmlyc3RcbiAgICBBIC0tPiBzZWNvbmRcbiAgICBBIC0tPiB0aGlyZFxuICAgIFxuICAgICBcblxuY2xhc3NEZWYgYmx1ZSBmaWxsOiNkZGQsc3Ryb2tlOiNmZmZmZmYsc3Ryb2tlLXdpZHRoOnB4LGNvbG9yOiMwMDAwMDAsIGZvbnQtc2l6ZToxNXB4O1xuY2xhc3NEZWYgd2hpdGUgZmlsbDojZmZmZmZmLHN0cm9rZTojMDAwLHN0cm9rZS13aWR0aDpweCxjb2xvcjojMDAwLGZvbnQtd2VpZ2h0OmJvbGRcbmNsYXNzRGVmIHNwYWNld2hpdGUgZmlsbDojZmZmZmZmLHN0cm9rZTojZmZmLHN0cm9rZS13aWR0aDowcHgsY29sb3I6IzAwMFxuY2xhc3MgQSxCLEMsRCxFLEYsRyxILE0sSixLLEwsTyxQLFEsUiBibHVlXG5jbGFzcyBTLFgsWSBzcGFjZXdoaXRlXG5jbGFzcyBmaXJzdCxzZWNvbmQsdGhpcmQgd2hpdGVcbiIsIm1lcm1haWQiOiJ7XG4gIFwidGhlbWVcIjogXCJkZWZhdWx0XCJcbn0iLCJ1cGRhdGVFZGl0b3IiOmZhbHNlLCJhdXRvU3luYyI6dHJ1ZSwidXBkYXRlRGlhZ3JhbSI6ZmFsc2V9)

### Using Hugo shortcode

K8s docs supports a Hugo shortcode for handling Mermaid figures.

* Use live editor to create and edit figures.

* Implemented and used for existing Mermaid figures.

* Easy to use by wrapping Mermaid code inside {{< mermaid >}} … {{</  mermaid >}} shortcode tags.

* In-line Mermaid code so contributors/reviewers can edit on the fly.

Note: Add the live editor URL link as a comment in your code so contributors/reviewers can view/edit/test the mermaid code.

### Using hybrid Mermaid+SVG

K8s docs supports SVG images. This method allows you to create/edit Mermaid figures in the live editor. Then from the live editor, you generate and download an SVG image file. Finally, add the SVG image to the docs as you would with any other SVG image.

* Use live editor to create and edit figures.

* Use live editor to generate and download SVG image.

* No change to existing K8s docs SVG image configuration. 

* Leverage new Mermaid features available in live editor. Those features might not be available in the current K8s/website version.

* Mermaid code is de-coupled from the K8s docs. In other words, new or edited figures show up in PRs as SVG images, not in-line Mermaid code.

Note: Add the live editor URL link as a comment block in the SVG file using your favorite text editor. Contributors/reviewers can then view/edit the mermaid code.

To add a comment to the SVG image file, use a text editor and add something like the following:

```mermaid
<!-- To view or edit the mermaid code, use the following URL: -->
<!-- https://mermaid-js.github.io/mermaid-live-editor/edit/#eyJjb ... -->
```

### Using native docsy

Note: Check closed PRs to see if K8s docs has enabled native docsy Mermaid support.

* Use live editor to create and edit figures.

* Easy to use by inserting Mermaid code inside a code block using ```mermaid …```.

* No need for shortcode tags.

* Inherits current Mermaid version from docsy.dev submodule.

* In-line Mermaid code so contributors/reviewers can edit on the fly.

Note: Add the live editor URL link as a comment in your code so contributors/reviewers can view/edit/test the mermaid code.

### Which method should I use?











    







