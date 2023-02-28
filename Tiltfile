# Build
custom_build(
	# Name of the container image
	ref = 'dispatcher-service',
	# Command to build th container image
	command = './mvnw spring-boot:build-image -Ddocker.name=$EXPECTED_REF',
	# Files to watch that trigger a new build
	deps = ['pom.xml', 'src']
)

# Deploy
k8s_yaml(kustomize('k8s))

# Manage
k8s_resource('dispatcher-service', port_forwards=['9003'])