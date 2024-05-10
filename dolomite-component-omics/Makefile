#
# Docker helper
#

no_cache=true
name=datashield/component-dolomite-omics
tag=latest

# Build Docker image
build-image:
	docker build --no-cache=$(no_cache) -t="${name}:$(tag)" .

push-image:
	docker image push ${name}:$(tag)
