import * as pulumi from "@pulumi/pulumi";
import * as github from "@pulumi/github";

// Create a new GitHub repository
const repo = new github.Repository("my-repo", {
    name: "my-repo",
    visibility: "public",
});

// Define a file in the repository
const repoFile = new github.RepositoryFile("my-file", {
    repository: repo.name,
    file: "README.md",
    content: "Hello, Pulumi!",
    commitMessage: "Initial commit",
});

// Export the repository URL
export const repoUrl = repo.htmlUrl;
// Create a new GitHub repository
const anotherRepo = new github.Repository("another-repo", {
    name: "another-repo",
    visibility: "public",
});
// Define a file in the repository
const anotherRepoFile = new github.RepositoryFile("another-file", {
    repository: anotherRepo.name,
    file: "README.md",
    content: "Hello again, Pulumi!",
    commitMessage: "Initial commit",
});
// Export the repository URL
export const anotherRepoUrl = anotherRepo.htmlUrl;