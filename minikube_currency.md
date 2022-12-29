Tasks | Details 
-- | --
Check the Latest stable version | **v1.28.0** (https://github.com/kubernetes/minikube/tree/v1.28.0)
Provide list of supported distros mentioned by community. Share link for reference.<br><br>Add support for following   Distros:<br>  RHEL 7.8, RHEL 7.9, RHEL 8.4, RHEL 8.6, RHEL 9.0, SLES12 SP5, SLES15 SP3, SLES15 SP4, Ubuntu 18.04(LTS), Ubuntu 20.04(LTS), Ubuntu 22.04 <br> Supported distro list should match   what community claims. If any community claimed distro is not worked on, give   appropriate reasons. |  **Community does not specify any particular linux distro but all linux distros are supported  for the given architectures - (https://minikube.sigs.k8s.io/docs/start/)**
Package   available in distribution? If yes, list distos along with versions available |  **SLES15-sp3 has 1.0.0-bp153.1.186**
Languages used – List all the languages used in Source. <br><br>Update the Package Status excel sheet <br>https://ibm.ent.box.com/file/910316005555 |   **Go 55.1%, HTML 35.9%, Shell 4.2%, Makefile 1.6%, C++ 1.5%, JavaScript 0.6%, Other 1.1%**
CI/CD info: <br> Community using any CI/CD tool? Yes/No<br>If yes, answer questions in the next column for each CI/CD tools<br><br>If Z is not already part of CI then look for chances to add Z support, share details like how to enable, etc, discussion is needed before we decide what to do.  | **Github Actions (https://github.com/kubernetes/minikube/actions)**<br>1. Is Z part of the CI? If yes, working properly & build succ? **No**<br> 2.  List archs being built**amd 64**<br>3. Is the package cross compiled? **No**<br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  **No**<br>5. Is this CI for build only? **Build and Test**<br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) **Functional Test, Unit Test, Lintall test**<br>7.   Is CI part of PR checks or PR merge commits? **Yes** <br><br>  **Jenkins ()**<br>1. Is Z part of the CI? If yes, working properly & build succ? **Yes**<br> 2.  List archs being built**amd64, arm, arm64, ppc64le, s390x**<br>3. Is the package cross compiled? **No**<br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  **Binary**<br>5. Is this CI for build only? **Build**<br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) **No**<br>7.   Is CI part of PR checks or PR merge commits? **No** <br><br>  **Prow (https://prow.k8s.io/job-history/gs/kubernetes-jenkins/pr-logs/directory/pull-minikube-build)<br>Used only to test Kubernetes with minikube(https://github.com/kubernetes/minikube/tree/master/deploy/prow)**<br>1. Is Z part of the CI? If yes, working properly & build succ? **no**<br> 2.  List archs being built**amd64**<br>3. Is the package cross compiled? **No**<br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  **No**<br>5. Is this CI for build only? **No**<br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) **No**<br>7.   Is CI part of PR checks or PR merge commits? **No** <br><br> **Google Cloud Build (https://pantheon.corp.google.com/cloud-build/dashboard?project=k8s-minikube)**<br>1. Is Z part of the CI? If yes, working properly & build succ? **No**<br> 2.  List archs being built**amd 64**<br>3. Is the package cross compiled? **No**<br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  **No**<br>5. Is this CI for build only? **Build **<br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) **No**<br>7.   Is CI part of PR checks or PR merge commits? **No** <br><br> **Azure Pipeline (https://dev.azure.com/medyagh0825/minikube-ci/_build)**<br>1. Is Z part of the CI? If yes, working properly & build succ? **No**<br> 2.  List archs being built**amd 64**<br>3. Is the package cross compiled? **No**<br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  **No**<br>5. Is this CI for build only? **Build **<br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) **No**<br>7.   Is CI part of PR checks or PR merge commits? **Yes** <br><br> **Travis CI (https://travis-ci.com/minikube-ci/examples/)**<br>1. Is Z part of the CI? If yes, working properly & build succ? **No**<br> 2.  List archs being built**amd 64**<br>3. Is the package cross compiled? **No**<br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  **No**<br>5. Is this CI for build only? **Build**<br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) **No**<br>7.   Is CI part of PR checks or PR merge commits? **Yes**<br><br> **Circle CI (https://circleci.com/gh/minikube-ci/examples)**<br>1. Is Z part of the CI? If yes, working properly & build succ? **No**<br> 2.  List archs being built**NA**<br>3. Is the package cross compiled? **No**<br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  **No**<br>5. Is this CI for build only? **No**<br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) **Yes,Smoke test(https://github.com/minikube-ci/examples/blob/master/.circleci/config.yml)**<br>7.   Is CI part of PR checks or PR merge commits? **Yes**<br><br> **GitLab CI (https://github.com/minikube-ci/examples/blob/master/.gitlab-ci.yml)**<br>1. Is Z part of the CI? If yes, working properly & build succ? **No**<br> 2.  List archs being built**amd 64**<br>3. Is the package cross compiled? **No**<br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  **No**<br>5. Is this CI for build only? **Build and test**<br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) **Yes, Functional Tests**<br>7.   Is CI part of PR checks or PR merge commits? **No**
Binary info:<br>Are Binaries (in any format) available? If yes, provide details: <br><br>If Binary is not available for Z then look for chances to add Z support, share details like how to enable, etc, discussion is needed before we decide what to do.  |  1.	List all architectures (including no-arch/no-mention) for which binaries are available and share link to download. **x86_64, ARM64, ARMv7, ppc643, s390x (https://github.com/kubernetes/minikube/releases/tag/v1.28.0)**<br>2. Provide details on how it is built e.g. cross vs native **cross**<br>3.	Tools being used to create binary **go**<br>4.	CI responsible for releasing the binary**jenkins**<br>5.	Is emulator used?**No**<br>6.	Verify/test binaries and share results.**Yes**
Docker Image info:<br> Dockerfile/images available externally for Intel?If Yes, provide details: <br> <br>If docker image is not available for Z then look for chances to add Z support, share details like how to enable, etc, discussion is needed before we decide what to do. |  **No**
Operator info:<br> Are Operators available?   If yes, provide details:| **No** 
PR info:<br> Are there any code changes needed for this release?If Yes, If yes, list them all in the next column and answer question for each. | **No code changes**
Issues info:| <br>1. Any issue created with community (GitHub, JIRA, Bugzilla etc)?If Yes, provide issue link.**No**<br>2. Check if there are existing open issues/PR’s and if it's still valid for this release.**No**  
Internal Deliverables: | 1.	Created Test reports (Table format)?Use test result template**No**<br>2.	Is Zenhub issue updated with all UpToDate info including informal community communications**Yes**<br>3.	List down detailed Steps followed to verify the package. Give reference link as well. Also Attach a proof of verification on the ZenHub issue**verified by starting cluster, checking web UI and creating a load balancer. **
External Deliverables: | 1.	Build Instructions<br>&nbsp;&nbsp;&nbsp;1.1	Is BI updated?**Yes**<br>&nbsp;&nbsp;&nbsp;1.2	List all the changes done with respect to published version**a)update to version 1.28.0<br>b)added support for Ub22.10, RHEL 8.7,9.1**<br>2.	Scripts  **Not maintained**<br>3.	Dockerfile   **Not maintained**<br>
External table changes required? Add details about external table changes required (If any) (Check links, distro etc.) | **No**
Actual efforts (In   hours) |  **18hrs**
Calendar   Time (actual Start and End Date in yyyy/mm/dd) |  **2022/12/27-2022/12/29**