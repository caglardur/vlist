<template>
	<v-container>
		<v-col>
			<v-row>
				<v-col>
					<v-card :border="true" height="200">
						<v-list :lines="false" density="compact" nav>
							<v-list-item v-for="(item, i) in items" :key="i" :value="item" active-color="primary" variant="flat" :to="{ name: item.text }">
								<template v-slot:prepend>
									<v-icon :icon="item.icon"></v-icon>
								</template>
								<v-list-item-title v-text="item.text"></v-list-item-title>
							</v-list-item>
						</v-list>
					</v-card>
				</v-col>
				<v-col>
					<v-card height="200" :border="true">
						<RouterView />
					</v-card>
				</v-col>
			</v-row>
		</v-col>
	</v-container>
</template>

<script lang="ts">
import { RouterView } from "vue-router"
export default {
	name: "App",
	data() {
		return {
			items: [
				{ text: "home", icon: "mdi-home" },
				{ text: "about", icon: "mdi-book-information-variant" },
				{ text: "list", icon: "mdi-clipboard-list" },
				{ text: "page", icon: "mdi-format-page-break" },
				{ text: "contact", icon: "mdi-email" }
			]
		}
	}
}
</script>
