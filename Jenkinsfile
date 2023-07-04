//
// Copyright (c) 2020 Intel Corporation
// Copyright (c) 2023 IOTech Ltd
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at
//
//      http://www.apache.org/licenses/LICENSE-2.0
//
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.
//

library(identifier: 'edgex-global-pipelines@main',
    retriever: legacySCM([
        $class: 'GitSCM',
        userRemoteConfigs: [[url: 'https://github.com/Ali-Amin/edgex-global-pipelines.git']],
        branches: [[name: '*/alvarium-integration']],
        doGenerateSubmoduleConfigurations: false,
        extensions: [[
            $class: 'SubmoduleOption',
            recursiveSubmodules: true,
        ]]]
    )
) _

edgeXBuildGoParallel(
    project: 'edgex-go',
    dockerFileGlobPath: 'cmd/**/Dockerfile',
    testScript: 'make test',
    buildScript: 'make build',
    publishSwaggerDocs: false,
    swaggerApiFolders: ['openapi/v3'],
    buildSnap: false,
    pushImage: false,
)
