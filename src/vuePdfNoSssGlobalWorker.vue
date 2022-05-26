<style src="./annotationLayer.css"></style>
<script>

	import componentFactory from './componentFactory.js'

	var component = componentFactory({});

	if ( process.env.VUE_ENV !== 'server' ) {
		var pdfjsWrapper = require('./pdfjsWrapper.js').default;
		var PDFJS = require('pdfjs-dist/es5/build/pdf.js');
		PDFJS.GlobalWorkerOptions.workerSrc = `//cdnjs.cloudflare.com/ajax/libs/pdf.js/${PDFJS.version}/pdf.worker.js`;
		component = componentFactory(pdfjsWrapper(PDFJS));
	}

	export default component;
</script>
