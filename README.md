This software is licensed under the Apache License, Version 2.0 (the "License");
you may not use this software except in compliance with the License.
You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

### Contrail source code instructions

Please follow the [instructions](http://juniper.github.io/contrail-vnc/README.html) in order to build the contrail
Virtual Network Controller source code.

###contrail.sh diff

    diff --git a/contrail.sh b/contrail.sh
    index 7628592..abdf586 100755
    --- a/contrail.sh
    +++ b/contrail.sh
    @@ -305,7 +305,7 @@ function download_dependencies {
             apt_get install default-jdk javahelper
             apt_get install libcommons-codec-java libhttpcore-java liblog4j1.2-java
                apt_get install python-software-properties
    -        sudo -E add-apt-repository -y cloud-archive:havana
    +        sudo -E add-apt-repository -y cloud-archive:kilo
             sudo -E add-apt-repository -y ppa:opencontrail
             apt_get update
     
    @@ -437,7 +437,8 @@ function repo_initialize {
                 fi    
             else
                 if [ $CONTRAIL_BRANCH ];then
    -                repo init -u https://github.com/juniper/contrail-vnc -b $CONTRAIL_BRANCH
    +                #repo init -u https://github.com/juniper/contrail-vnc -b $CONTRAIL_BRANCH
    +                repo init -u https://github.com/sajuptpm/contrail-vnc -b R2.1_debug
                     rev_original="refs\/heads\/master"
                     rev_new="refs\/heads\/"$CONTRAIL_BRANCH 
                    sed -i "s/$rev_original/$rev_new/" .repo/manifest.xml


