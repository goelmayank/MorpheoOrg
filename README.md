# MorpheoOrg

##Changes made to original Morpheo project
find and replace channel-artifacts with artifacts

example.com										:	morpheo.co
org1											:	aphp

github.com/chaincode/chaincode_example02/go/	:	github.com/chaincode/


/opt/gopath/src/github.com/chaincode 			:	

./../chaincode/									:	./../morpheo-orchestrator-chaincode/

change ownership of folder morpheo-dev-env/data
edit mapping of secrets/crypto-config in morpheo-devenv/docker-composer.yaml

change Org1 to Aphp in morpheo-fabric-bootstrap/crypto-config.yaml
change line 182,262,267 in scripts/utils.sh to reflect orchestrator arguments

changed restart to no in morpheo-storage/docker-composer.yaml
changed restart to no in morpheo-devenv/docker-composer.yaml line 8


##cleaning
remove org2
//note remove eyfn.sh and org3-artifacts.sh and scripts.sh

##testing
peer chaincode invoke -o orderer.morpheo.co:7050 --tls true --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/morpheo.co/orderers/orderer.morpheo.co/msp/tlscacerts/tlsca.morpheo.co-cert.pem -n mycc -c '{"Args":["registerProblem", "e568587d-572c-4714-8084-378ed50d1c52", "2", "0pa81bfc-b5f4-5ba2-b81a-b464248f02a1, 0kk81bfc-b5f4-5ba2-b81a-b464248f02e3"]}' -C mychannel

peer chaincode invoke -o orderer.morpheo.co:7050 --tls true --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/morpheo.co/orderers/orderer.morpheo.co/msp/tlscacerts/tlsca.morpheo.co-cert.pem -n mycc -c '{"Args":["registerItem", "algo", "0pa81baa-b5f4-5ba2-b81a-b464248f02d2", "problem_1", "mytopalgo"]}' -C mychannel